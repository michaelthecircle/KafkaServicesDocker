# Конфигурация Docker-Compose

**Конфигурация используется для запуска приложения, включающего следующие компоненты:**
- **PostgreSQL** и **pgAdmin**: для управления базой данных PostgreSQL, хранящей информацию о правилах фильтрации, дедубликации и обогащения.
- **Liquibase**: для выполнения миграций базы данных.
- **Kafka и Zookeeper**: для обмена сообщениями между сервисами.
- **Redis**: для хранения дублей.
- **MongoDB** и **Mongo Express**: для хранения правил обогащения.
- **Микросервисы**: для выполнения бизнес-логик фильтрации, дедупликации, обогащения сообщений из kafka и управления правилами.
    - Сервис фильтрации https://github.com/michaelthecircle/JavaServiceFiltering
    - Сервис дедубликации https://github.com/michaelthecircle/JavaServiceDeduplication
    - Сервис обогащения https://github.com/michaelthecircle/JavaServiceEnrichment
    - Сервис менеджер https://github.com/michaelthecircle/JavaServiceManagement
- **backend**: все сервисы находятся в одной сети для обеспечения взаимодействия между ними.
### Использование
- Убедитесь, что Docker и Docker Compose установлены на вашем компьютере.
- запустите команду docker-compose up для старта всех сервисов.
```shell
docker compose up
```
### Сервисы будут доступны на соответствующих портах, указанных в конфигурации.

- pgAdmin: 5433
- Mongo Express: 12080
- Микросервисы:
    - Service Filtering: 8081
    - Service Deduplication: 8082
    - Service Enrichment: 8083
    - Service Management: 8084/actuator
