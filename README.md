# jbnc
## Bouncer with no authentication required written in nodejs with support for separate client buffers for playback history, an always-on connection, and SSL with stunnel.

### Purpose
Bouncers are hard to configure.  I felt that we needed an easier one in this world.  This takes requires no configuration to connect!

### Features
- Always on connection to IRC
- No registration or account required
- Separate buffers for clients possible
- SSL with stunnel

### Setup / Installation
1. Clone the repo
```
git clone https://github.com/realrasengan/jbnc
```

2. Run
```
node bouncer.js
```

#### SSL
1. On Ubuntu
```
sudo apt install stunnel
```

2. Get an SSL cert from Let's Encrypt

3. Edit /etc/stunnel/stunnel.conf
```
cert = /etc/stunnel/cert.pem
key  = /etc/stunnel/cert.key
client = no

[jbnc]
accept = 9999
connect = 8888
```

### IRC Client
You just need to set your password:
For an open bouncer
```
PasswordGoesHere/ServerGoesHere
```

For a password protected one
```
ServerPassword||PasswordGoesHere/ServerGoesHere
```

To save clientbuffers for your client
```
PasswordGoesHere/ServerGoesHere/deviceid
```

Here is an example for a desktop and mobile setup with a password protected server connecting to DALnet:
```
dragon||AJFiej2fn2345/irc.dal.net:6667/desktop
dragon||AJFiej2fn2345/irc.dal.net:6667/mobile
```

### Copyright
(c) 2020 Andrew Lee <andrew@imperialfamily.com>
All Rights Reserved.

MIT LICENSED