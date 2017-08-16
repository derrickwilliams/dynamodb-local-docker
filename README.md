```bash
docker-compose up
aws dynamodb create-table --endpoint http://localhost:8008 --cli-input-json file://seed/create-notifications.json
aws dynamodb put-item --endpoint http://localhost:8008 --table-name OnboardingNotifications --item file://seed/item.json
aws dynamodb scan --endpoint http://localhost:8008 --table-name OnboardingNotifications
```