# Уводмление о новом подключении к SSH
Скрипт на ZSH, который уведомит вас в телеграмме о новом подключении к SSH.

## Установка
Раскидываем файлы по директориям
```sh
sudo cp telegram-ssh-notify /usr/local/lib
sudo chmod 755 /usr/local/lib/telegram-ssh-notify

sudo cp telegram-ssh-notify.env /etc
sudo chmod 600 /etc/telegram-ssh-notify.env

sudo cp telegram-ssh-notify.service /etc/systemd/system/
sudo chmod 644 /etc/systemd/system/telegram-ssh-notify.service

sudo systemctl daemon-reload
```

После чего, нужно включить сервис
```sh
sudo systemctl enable --now telegram-ssh-notify.service
```

После отредактируйте файл /etc/telegram-ssh-notify.env, вставив туда нужные значения.

## Переменные окружения
- `TG_TOKEN` - API-токен телеграмма (Получить можно у [@BotFather](https://t.me/BotFather)).
- `TG_USER` - ID вашего пользователя.
- `SYSTEMD_DAEMON` - Назваение SSH-сервиса.
