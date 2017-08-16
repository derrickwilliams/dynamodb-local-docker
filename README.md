```bash
docker-compose up
aws dynamodb create-table --endpoint http://localhost:8008 --cli-input-json file://seed/create-notifications.json
aws dynamodb put-item --endpoint http://localhost:8008 --table-name OnboardingNotifications --item file://seed/item.json
aws dynamodb scan --endpoint http://localhost:8008 --table-name OnboardingNotifications
```

 open `localhost:8008/shell` for a javascript shell where you can interact with the running instance