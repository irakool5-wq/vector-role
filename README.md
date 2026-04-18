# Vector Role
Role для установки и настройки [Vector]

## Требования
- Ansible 2.1+
- Python 3
- Поддерживаемые ОС: Ubuntu 20.04+, Debian 11+

## Переменные

| Переменная | Описание | Значение по умолчанию |
|-----------|---------|---------------------|
| `vector_version` | Версия Vector для установки | `"0.34.1"` |
| `vector_arch` | Архитектура (x86_64, aarch64) | `"x86_64"` |
| `vector_log_level` | Уровень логирования | `"info"` |
| `clickhouse_endpoint` | Endpoint ClickHouse для отправки данных | `"http://localhost:8123"` |
| `clickhouse_database` | Имя БД в ClickHouse | `"logs"` |
| `clickhouse_table` | Имя таблицы в ClickHouse | `"vector_logs"` |

### Пример использования в playbook

```yaml
- hosts: monitoring
  roles:
    - role: vector-role
      vars:
        vector_log_level: "debug"
        clickhouse_endpoint: "http://clickhouse.prod:8123"