# DevOps #

## Setup Webhook on Ubuntu ##
install [webhook](https://github.com/adnanh/webhook), see guide for [installation](https://github.com/adnanh/webhook)

```sudo apt-get install webhook```

create webhook directory file
```
mkdir webhook
```

create hooks.json file
```
sudo vim hooks.json
```

hooks.json
```
[
  {
    "id": "repository_name",
    "execute-command": "/home/webhook/redeploy.sh",
    "command-working-directory": "/home/your_repository_directory"
  }
]
```

create shebang file "redeploy.sh"
```
sudo vim redeploy.sh
```

redeploy.sh
```
#!/bin/sh

git pull
git reset --hard origin/webhook_branch
npm install -f
npm run build
/pm2-directory restart all
```

set permission
```
sudo chmod +x /home/webhook/redeploy.sh
```

and run webhook (to see which its located)
```
which webhook
```
and run it

```
/usr/bin/webhook -hooks ~/webhook/hooks.json -verbose -port 9000
```

check if it running on port 9000
```
netstat -tulpn
```
