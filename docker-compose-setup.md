# docker compose Setup in ubuntu Linux VM #

## Step - 1 : Create Linux VM ##

1) Create Ubuntu VM using AWS EC2 (t2.medium or t2.micro) <br/>

3) Connect to VM using MobaXterm

## Step-2 : Install Required Packages ##

```
sudo apt update
sudo apt install ca-certificates curl
```

## Step-3 : Add Docker Repository ##
```
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc


```

## Step-4 : Set read permissions for the key ##
```
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

## Step-5 :  Add the Docker repository to the list of APT sources ## 

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```

## Step-6 : Install Docker Compose Plugin ##

```
sudo apt update
sudo apt install docker-compose-plugin -y
docker compose version

```
