---
layout: post
title:  Jekyll blog with docker
categories: webdev, docker, tech
usemathjax: true
---

# Building a blog with Jekyll and Docker

An easy guide and reference (mainly for myself). Probably not following best practices but it works.

After reading the guide we'll have a functional blog built by Jekyll, run locally in a container using Docker.

## Setting up the environment

I am using Ubuntu. Get the Docker cli from the store or use
```
sudo snap install docker
```
to do it through the terminal.

Visual Studio Code is an excellent editor that also has terminal.
```
sudo snap install code --classic
```
We might also need `git` and `curl`:
```
sudo apt install git curl
```
Now, we need to create our working directory. I already have my blog created so I `git clone` it. If you don't have that, the only thing we need is an empty directory inside of which we are going to create the **Dockerfile**.

The **Dockerfile** contains instructions on how the image is built, i.e. how the initial state of our container will look. We can create many containers using the same image. So, without further ado, we are going to create a  new  text file called *Dockerfile* and write the following text in it:
```
    FROM ruby:3.4.2-alpine3.21

    RUN apk update
    RUN apk add --no-cache build-base gcc cmake git
    
    RUN gem update bundler && gem install bundler jekyll
```
This will instruct docker to create an *alpine* image (a minimal linux distribution) that includes ruby, update its packages, install some development tools and also install the *bundler* and *jekyll* gems (ruby packages).

Now we need to create the image:
```
docker build -t yourname/ruby .
```
This command will download the required files so it can create an image of the OS using the instructions provided inside the Dockerfile. Now we need to create a container, mount our working directory to it, expose some ports and get a bash shell so we can run commands inside the container. We will use the `docker run` command along with some flags and arguments:
```
docker run -it -v /path_to_working_dir/:/home/dev/blog -w /home/dev/blog --publish 8080:8080 your_image_name  sh
```
The flags `-i`, `-t` or `-it` give us the option to have an interactive session with a terminal. The `-v` flag is used to mount a directory from the host system (for me it's the location of the cloned repository. All my files will then be shown in the container) for which we specify the directory we need to work in and its location inside the  container. `-w` will mark the working directory so we get faster access to it. Finally, we expose some ports and also get a terminal wish sh.

After running this command, we can get into the container by
```
docker start -ai container_name
```
Now we have a fully working container which we can use to develop our blog. We can now follow exactly the instructions from the jekyll website in order to create a sample blog: `jekyll new .` (don't omit the dot!), `bundle exec jekyll serve --host 0.0.0.0 --port 8080`.

*If you get an error (seg fault) there is a workaround [here](https://github.com/protocolbuffers/protobuf/issues/16853).*

You can see what you made by opening the local address [http://0.0.0.0:8080](http://0.0.0.0:8080).