## Packer docker nginx
A packer template that builds docker image with nginx and a vagrant file for a docker machine.

#### Prerequisites:
* Install Vagrant - [installation instructions](https://www.vagrantup.com/downloads.html)

#### Setting up Vagrant environment:
* Build the VM - run: `vagrant up`
* Login to VM - run: `vagrant ssh -c "sudo su -"`
* Get the git repo - run: `git clone https://github.com/slavrd/packer-docker-nginx.git` and `cd packer-docker-nginx`

#### Building the Image:
* Run: `packer build template.json`<br>
The image will be commited to the local registry.

#### Checking the Image:
* Get the image id: `docker image ls`
* Run a container from the image: `docker run -d -p 4000:80 <image_id>`
* The nginx server from the image should be accessible on localhost:4000 e.g. `curl localhost:4000`
