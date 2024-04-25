# Variables

## Docker

| Variable Name | Description | Type | Default Value |
|---|---|---|---|
| docker_compose_directory | The directory where Docker Compose files are stored | String | "/opt/docker-compose" |
| docker_compose_bin | The Docker Compose binary to use | String | "docker compose" |

## Prometheus

| Variable Name | Description | Type | Default Value |
|---|---|---|---|
| prometheus_docker_network | The name of the Docker network for Prometheus containers | String | "prometheus" |
| prometheus_docker_pull | Whether to pull the Prometheus Docker image | String | "no" |
| prometheus_os | The operating system for Prometheus | String | "linux" |
| prometheus_arch | The architecture for Prometheus | String | "amd64" |
| prometheus_repo | The repository URL for Prometheus | String | "" |
| prometheus_nodes_ip | The IP addresses of Prometheus nodes | Dictionary | localhost: "127.0.0.1" |
| prometheus_retention_time | The retention time for Prometheus data | String | "15d" |
| prometheus_server_enable | Whether to enable the Prometheus server | Boolean | false |
| prometheus_use_victoriametrics | Use VictoriaMetrics as prometheus backend | Boolean | false |
| prometheus_server_global_evaluation_interval | The global evaluation interval for Prometheus server | Integer | 15 |
| prometheus_server_global_scrape_interval | The global scrape interval for Prometheus server | Integer | 15 |
| prometheus_server_job_name | The job name for Prometheus server | String | "prometheus" |
| prometheus_server_scrape_interval | The scrape interval for Prometheus server | Integer | 5 |
| prometheus_server_scrape_timeout | The scrape timeout for Prometheus server | Integer | 5 |
| prometheus_server_version | The version of Prometheus server to install | String | "latest" |
| prometheus_watchtower_enable | Whether to enable watchtower on this container | Boolean | true |

## Prometheus Exporters

| Variable Name | Description | Type | Default Value |
|---|---|---|---|
| exporter_upgrade | Whether to upgrade the exporter | String | "" |
| prometheus_exporters_repo | The repository URL for Prometheus exporters | String | "https://git.rznet.fr/tchivert/prometheus_exporters" |
| prometheus_exporters_release | The release version of Prometheus exporters | String | "latest" |
| prometheus_exporters_sources | The source of Prometheus exporters (repo or origin) | String | "repo" |
| prometheus_repo_apache | Apache exporter repository | String | Lusitaniae |
| prometheus_repo_blackbox | Blackbox exporter repository | String | prometheus |
| prometheus_repo_memcached | Memcached exporter repository | String | prometheus |
| prometheus_repo_mongodb | MongoDB exporter repository | String | percona |
| prometheus_repo_mysqld | MySQLd exporter repository | String | prometheus |
| prometheus_repo_nginx | Nginx exporter repository | String | tchivert |
| prometheus_repo_node | Node exporter repository | String | prometheus |
| prometheus_repo_opcache | Opcache exporter repository | String | tchivert |
| prometheus_repo_phpfpm | PHP-FPM exporter repository | String | Lusitaniae |
| prometheus_repo_postgres | Postgres exporter repository | String | prometheus-community |
| prometheus_repo_redis | Redis exporter repository | String | tchivert |
| prometheus_repo_varnish | Varnish exporter repository | String | tchivert |
| prometheus_exporter_packages | The list of exporter packages to install | List | [] |
| prometheus_apache_port | The port for Apache exporter | Integer | 8080 |
| prometheus_blackbox_exporter_host | The host for Blackbox exporter | String | localhost |
| prometheus_mongodb_exporter_database | The database for MongoDB exporter | String | "admin" |
| prometheus_mongodb_exporter_host | The host for MongoDB exporter | String | "localhost" |
| prometheus_mongodb_exporter_port | The port for MongoDB exporter | Integer | 27017 |
| prometheus_opcache_exporter_fcgi_uri | The FCGI URI for Opcache exporter | String | "unix:///var/run/www.sock" |
| prometheus_phpfpm_sockets_directory | The directory for PHP-FPM sockets | String | "/run/php/" |
| prometheus_postgres_exporter_systemd_user | The systemd user for Postgres exporter | String | "postgres" |
| prometheus_postgres_exporter_host | The host for Postgres exporter | String | "/var/run/postgresql/" |
| prometheus_postgres_exporter_sslmode | The SSL mode for Postgres exporter | String | "disable" |
| prometheus_postgres_exporter_user | The user for Postgres exporter | String | "postgres" |
| prometheus_postgres_exporter_password | The password for Postgres exporter | String | "changeme_" |
| prometheus_postgres_exporter_port | The port for Postgres exporter | Integer | 5432 |
| prometheus_proxmox_exporter_user | Username used to contact Proxmox API | String | "" |
| prometheus_proxmox_exporter_password | Password for previous username | String | "" |
| prometheus_proxmox_exporter_node | Proxmox node to metrics from | String | "" |
| prometheus_redis_exporter_addr | The address for Redis exporter | String | "redis://localhost:6379" |
| prometheus_redis_exporter_user | The user for Redis exporter | String | "" |
| prometheus_redis_exporter_password | The password for Redis exporter | String | "" |

## Grafana

| Variable Name | Description | Type | Default Value |
|---|---|---|---|
| grafana_auth_anonymous_enabled | Whether anonymous authentication is enabled in Grafana | Boolean | false |
| grafana_auth_anonymous_org_role | The role for anonymous users in Grafana | String | Editor |
| grafana_auth_anonymous_org_name | The name of the organization for anonymous users in Grafana | String | 'Main Org.' |
| grafana_auth_disable_login_form | Whether to disable the login form in Grafana | Boolean | false |
| grafana_editors_can_admin | Whether editors can administer Grafana | Boolean | false |
| grafana_users_viewers_can_edit | Whether viewers can edit in Grafana | Boolean | false |
| grafana_log_level | The log level for Grafana | String | error |
| grafana_router_logging | Whether to enable router logging in Grafana | Boolean | false |
| grafana_disable_sanitize_html | Whether to disable HTML sanitization in Grafana | Boolean | true |
| grafana_traefik_entrypoint | The Traefik entrypoint for Grafana | String | 'websecure' |
| grafana_watchtower_enable | Whether to enable watchtower on this container | Boolean | true |
