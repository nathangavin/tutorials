#Docker commands for installing and configuring docker on a machine.

1. follow tutorial found here: https://docs.docker.com/engine/install/debian/#install-using-the-repository

```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo 
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian 
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | 
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

2. attempt to verify installation:

`sudo docker run hello-world`

(you will likely get an error about the deamon not running.)


3. start the deamon:

try this, though it probably wont work:

`sudo systemctl start docker`

Alternatively, run this in a terminal then just work in another:

`sudo dockerd`
(this one should work)

===============================

#Useful commands for docker

* `docker images`
    * shows list of built images
* `docker build -t [name] [location]`
    * builds a docker image, called [name], & with the dockerfile located at [location]
    * e.g. `docker build -t backend .`
        * this builds an image called backend, using the dockerfile in the current directory
* `docker run -p [in port:out port] --name [image name] -d [instance name]`
    * gets the built image and runs it, setting the ports to the defined ports and sets the running instance to the defined instance name
    * e.g. `docker run -p 3306:3306 --name backend -d backend`
* `docker stop [instance name]`
    * stops the named instance, note different to the image name
* `docker rm/remove [container]`
    * deletes the container/instance
* `docker start [container name]`
    * restarts stopped instance
* `docker container ls -a`
    * shows a list of containers/instances

