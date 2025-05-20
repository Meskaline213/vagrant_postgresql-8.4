# Vagrant + PostgreSQL 8.4 (Ubuntu 12.04)

Этот проект позволяет быстро развернуть виртуальную машину с Ubuntu 12.04 и PostgreSQL 8.4 с помощью Vagrant и VirtualBox.

## Требования
- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Как использовать

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/Meskaline213/vagrant_postgresql-8.4.git
   cd vagrant_postgresql-8.4
   ```
2. Запустите виртуальную машину:
   ```bash
   vagrant up
   ```
3. Подключитесь к машине:
   ```bash
   vagrant ssh
   ```
4. Проверьте PostgreSQL:
   ```bash
   psql --version
   sudo -u postgres psql
   ```

## Важно
- В процессе установки могут появляться предупреждения и сообщения об устаревших пакетах — это нормально для старых версий Ubuntu и PostgreSQL.
- Если появится диалог debconf (об obsolete major version), просто нажмите Enter/Ok или выполните внутри VM:
  ```bash
  sudo dpkg --configure -a
  sudo service postgresql start
  ```
- После установки PostgreSQL 8.4 будет работать.

## Для чего это нужно

Такой подход позволяет запускать старый код, который требует специфических версий ПО, в изолированной среде.

---

**Внимание!** Не используйте данную конфигурацию для продакшена — только для тестов и учебных целей.
