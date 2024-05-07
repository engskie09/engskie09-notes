# Linux/Ubuntu #


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
nvm use <version>
```