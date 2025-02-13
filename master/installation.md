# Installation

[[toc]]

::: warning WARNING
Pixelfed is still a work in progress. We do not recommending running an instance in production unless you know what you are doing!
:::

## Download Source via Git

```bash
$ cd /home # Or wherever you chose to install web applications
$ git clone -b dev https://github.com/pixelfed/pixelfed.git pixelfed
$ cd pixelfed
```

## Basic Configuration


::: tip
You can find a list of additional configuration settings on the [Configuration](configuration.html) page.
:::

By default Pixelfed comes with a ```.env.example``` file. You'll need to rename this file to just ```.env``` regardless of what environment you're working on.

It's now just a case of editing this new ```.env``` file and setting the values of your setup.


```text
APP_NAME="PixelFed Test"
APP_ENV=production
APP_KEY=
APP_DEBUG=false
APP_URL=http://localhost

ADMIN_DOMAIN="localhost"
APP_DOMAIN="localhost"

LOG_CHANNEL=stack

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=
DB_USERNAME=
DB_PASSWORD=

BROADCAST_DRIVER=log
CACHE_DRIVER=redis
SESSION_DRIVER=redis
SESSION_LIFETIME=120
QUEUE_DRIVER=redis

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_DRIVER=log
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="Pixelfed@example.com"
MAIL_FROM_NAME="Pixelfed"

SESSION_DOMAIN="${APP_DOMAIN}"
SESSION_SECURE_COOKIE=true
API_BASE="/api/1/"
API_SEARCH="/api/search"

OPEN_REGISTRATION=true
RECAPTCHA_ENABLED=false
ENFORCE_EMAIL_VERIFICATION=true

MAX_PHOTO_SIZE=15000
MAX_CAPTION_LENGTH=150
MAX_ALBUM_LENGTH=4

MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
MIX_APP_URL="${APP_URL}"
MIX_API_BASE="${API_BASE}"
MIX_API_SEARCH="${API_SEARCH}"

ACTIVITYPUB_INBOX=false
ACTIVITYPUB_SHAREDINBOX=false
HORIZON_DARKMODE=true

# Set these both "true" to enable federation.
# You might need to also run:
#   php artisan cache:clear
#   php artisan optimize:clear
#   php artisan optimize
ACTIVITY_PUB=false
REMOTE_FOLLOW=false
```

Then you need to setup the secret key:
```
php artisan key:generate
```