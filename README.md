Seyren-Init
===========

Init.d Script for Seyren

This is an init.d script for [Seyren](https://github.com/scobal/seyren#Key) which allows you to start the service.

To use this you will need to make the below amendments for your environment

Instructions

1. Copy the seyren init.d script to /etc/init.d/ of the server that its installed on.
2. Amend the permissions of the seyren script so that its runnable (eg chmod 777 seyren)
3. Amend the Core environment parameters in the init.d script for your environment detailed below.

init.d environment variables

`GRAPHITE_URL`="http://graphite.somewebsite.com"
export GRAPHITE_URL

`SMTP_HOST`="smtp.host.com"
export SMTP_HOST

`SMTP_PORT`="25"
export SMTP_PORT

There are further environment variables that can be added if needed which are not currently in the script, 
however feel free to amend this for your needs as necessary.

##Full Environment list

#### Base
* `GRAPHITE_URL` - The location of your graphite server. Default: `http://localhost:80`
* `GRAPHITE_USERNAME` - The Http Basic auth username for the graphite server. Default: ``
* `GRAPHITE_PASSWORD` - The Http Basic auth password for the graphite server. Default: ``
* `GRAPHITE_KEYSTORE` - The Http KeyStore path for the https graphite server. Default: ``
* `GRAPHITE_KEYSTORE_PASSWORD` - The Http KeyStore password for the https graphite server. Default: ``
* `GRAPHITE_TRUSTSTORE` - The Http TrustStore path for the https graphite server. Default: ``
* `MONGO_URL` - The mongo connection string. Default: `mongodb://localhost:27017/seyren`
* `SEYREN_URL` - The location of your seyren instance. Default: `http://localhost:8080/seyren`

#### SMTP
* `SMTP_HOST` - The smtp server to send email notifications from. Default: `localhost`
* `SMTP_PORT` - The smtp server port. Default: `25`
* `SMTP_FROM` - The from email address for sending out notifications. Default: `alert@seyren`
* `SMTP_USERNAME` - The smtp server username if authenticated SMTP is used. Default: ``
* `SMTP_PASSWORD` - The smtp server password if authenticated SMTP is used. Default: ``
* `SMTP_PROTOCOL` - The smtp server protocol if authenticated SMTP is used. Default: `smtp`

#### HipChat
* `HIPCHAT_AUTHTOKEN` - The hipchat api auth token. Default: ``
* `HIPCHAT_USERNAME` - The username that messages will be sent from. Default: `Seyren Alert`

#### PagerDuty
* `PAGERDUTY_DOMAIN` - The PagerDuty domain to be notified. Default: ``
* `PAGERDUTY_USERNAME` - The PagerDuty API username. Default: ``
* `PAGERDUTY_PASSWORD` - The PagerDuty API Password. Default: ``

#### Hubot
* `HUBOT_URL` - The location where Hubot is running. Default ``

#### Flowdock
* `FLOWDOCK_EXTERNAL_USERNAME` - The username that messages will be sent from to a flow. Default: `Seyren`
* `FLOWDOCK_TAGS` -  Special tags to add to all messages. Default: ``
* `FLOWDOCK_EMOJIS` - Mapping between state and emojis unicode. Default: ``
