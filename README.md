# Ansible-Playbook для ClickHouse и Vector

## Оглавление
- [Введение](#введение)
- [Компоненты Playbook](#компоненты-playbook)
  - [ClickHouse](#clickhouse)
  - [Vector](#vector)
  - [LightHouse](#lighthouse)
- [Процесс Установки](#процесс-установки)
- [Установка и Настройка](#установка-и-настройка)
  - [Предварительные условия](#предварительные-условия)
  - [Настройка](#настройка)
  - [Установка](#установка)
  - [Конфигурация Vector](#конфигурация-vector)
  - [Конфигурация Nginx](#конфигурация-nginx)

## Введение
Этот репозиторий содержит Ansible Playbook для установки и настройки сервера ClickHouse, инструмента Vector и веб-сервера LightHouse.

## Компоненты Playbook

### ClickHouse
Установка и настройка сервера ClickHouse для обработки и анализа больших объемов данных.

### Vector
Конфигурация и установка Vector для сбора, преобразования и отправки логов.

### LightHouse
Настройка веб-сервера Nginx для LightHouse - инструмента визуализации данных.

## Установка и Настройка

### Предварительные условия
- Ansible 2.9 или выше.
- SSH доступ к целевым серверам.

### Настройка
Используйте `prod.yml` для настройки хостов и `vars.yml` для определения версий компонентов.

### Установка
Запустите Playbook командой: `ansible-playbook -i inventory/prod.yml site.yml`.

### Конфигурация Vector
Vector настраивается для сбора и обработки логов с помощью шаблона `vector_config.j2`.

### Конфигурация Nginx
Nginx настраивается с использованием шаблона `nginx_config.j2`, который включает конфигурацию сервера для оптимальной работы с ClickHouse и Vector.