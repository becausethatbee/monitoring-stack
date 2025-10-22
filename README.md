# Prometheus Monitoring Stack

Полная настройка мониторинга инфраструктуры через Docker Compose: Prometheus, Node-exporter, cAdvisor, Grafana, Alertmanager с проксированием через HAProxy.

## Структура

- `prometheus/` - Конфигурация Prometheus, правила алертинга, TSDB
- `grafana/` - Данные Grafana (dashboards, datasources, users)
- `alertmanager/` - Конфигурация Alertmanager
- `docker-compose.yml` - Основная конфигурация стека

## Быстрый старт
```bash
cd ~/monitoring-stack
mkdir -p prometheus/data grafana/data alertmanager/data
docker compose up -d
```

## Документация

[Полная документация](./docs/prometheus-docker-stack.md)

## Доступ

- **Prometheus**: http://\<SERVER_IP\>:8444/prometheus/
- **Grafana**: http://\<SERVER_IP\>:8444/grafana/ (логин: admin/admin)
- **Alertmanager**: http://\<SERVER_IP\>:8444/alertmanager/

Аутентификация через HAProxy (базовая HTTP).

## Компоненты

- **Prometheus** v3.7.1 - Time-series database
- **Node-exporter** v1.8.2 - Метрики хоста
- **cAdvisor** v0.49.1 - Метрики контейнеров
- **Grafana** 12.2.0 - Визуализация (порт 3200)
- **Alertmanager** v0.27.0 - Маршрутизация алертов

## Требования

- Docker и Docker Compose
- HAProxy с сетью 
- Открытый порт 8444/tcp

## Troubleshooting

