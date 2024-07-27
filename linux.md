# Linux #
| Command | e.g. | Description
| --- | --- | ---
| ```which``` | which webhook | show current directory of a file
| ```mv``` | mv oldName.sh newName.sh | rename a file
| ```netstat -tulpn``` | | display port with process/app
| ```ps -ef &#124; grep nohup``` | | display nohup processes
| ```kill -9 [pid]``` | kill -9 10000 | force kill process by id
| ```pkill -9 [pname]``` | pkill -9 node | force kill process by name

## Node Version Manager (NVM) ##
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```
```
source ~/.bashrc
```
```
nvm install stable
```
```
nvm use <version>
```

## Git ##
Install Git on Ubuntu. See guide [Git Installation](https://github.com/git-guides/install-git#install-git-on-linux)
```
sudo apt-get update
```
```
sudo apt-get install git-all
```
```
git version
````

## Nginx ##
 Git on Ubuntu. See guide [Git Installation](https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source)
```
sudo apt-get update
```
```
sudo apt-get install nginx
```
```
sudo nginx -v
```
