for azure

transfer files from windows:
scp -i C:/path.pem fullchain.pem private-key.pem azureuser@127.0.0.1:/home/azureuser/

sudo mkdir -p /etc/nginx/ssl
sudo mv ~/fullchain.pem /etc/nginx/ssl/
sudo mv ~/private-key.pem /etc/nginx/ssl/
sudo chmod 600 /etc/nginx/ssl/*
