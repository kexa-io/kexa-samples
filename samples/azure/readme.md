create a temporary service principal:
```
az ad sp create-for-rbac --name "kexa-$(date +%F)-test"
```

add rbac for this service princial reader on subscription
in command for all your subscriptions

```
SP_NAME="kexa-$(date +%F)-test"
SP_APP_ID=$(az ad sp list --display-name "$SP_NAME" --query "[0].appId" -o tsv)
SUBSCRIPTION_IDS=$(az account list --query "[].id" -o tsv)
for SUB_ID in $SUBSCRIPTION_IDS
do
    echo "➡️ 'Reader'  : $SUB_ID"
    az role assignment create \
        --assignee "$SP_APP_ID" \
        --role "Reader" \
        --scope "/subscriptions/$SUB_ID" \
        -o none 

    echo ""
done
```

copy .env-sample to .env
```
cp .env-sample .env
```

replace values
run docker-compose

```
docker-compose up
```

change rules/azure.yaml as you want
