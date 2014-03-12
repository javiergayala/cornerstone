# Cornerstone

http://rackerlabs.github.io/cornerstone/

HarpJS application to house custom CSS framework

## Quickstart

CSS files ready for use:

http://rackerlabs.github.io/cornerstone/css/main.css

http://rackerlabs.github.io/cornerstone/css/responsive.css

http://rackerlabs.github.io/cornerstone/css/tooltips.css

## Installation

### Installing Required Packages

1. [Install Ruby](https://www.ruby-lang.org/en/installation/) if not present on the system.
2. [Install Gem](http://rubygems.org/pages/download) if not present on the system.
3. [Install Node and NPM](http://nodejs.org/download/) if not present on the system.
4. [Install Git](http://git-scm.com/downloads) if not present on the system.
5. Install Jekyll using gem - `sudo gem install jekyll`
6. Install gulp.js globally using npm - `sudo npm install -g gulp`

### Setup Project for Editing

1. Clone the vermeer branch of this repo - `git clone https://github.com/troyswanson/cornerstone --branch vermeer`
2. Move to the directory - `cd cornerstone`
3. Install dependencies using npm - `npm install`
4. Build SASS files using gulp.js - `gulp sass`
5. Build branch files using jekyll - `jekyll build`
6. Move to site directory - `cd site`
7. Serve site via jekyll - `jekyll serve`

## Updating Content

All content is contained in the /site/docs directory in a $section.md file. 

Content is written in markdown. A helpful hint sheet for markdown syntax can be found [here](http://daringfireball.net/projects/markdown/syntax).

Actions that can be taken in the 

### Adding Content

## Additional

### HarpJS Container setup

1. [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. [Install Vagrant](http://downloads.vagrantup.com/)
3. Set `FORWARD_DOCKER_PORTS` env variable (See [Vagrantfile](https://github.com/rackerlabs/cornerstone/blob/master/Vagrantfile#L88))
4. `vagrant up` (Will take a cople of minutes to boot first time)
5. `vagrant ssh`
6. Navigate to `/vagrant` (should map to cloned repo directory)
7. `sudo docker build -t cornerstone .`

### HarpJS Container usage

*From within Vagrant Box*

#### Interactive Server

```bash
sudo docker run -i -t -p 49000:9000 -v /vagrant/:/mnt/cornerstone:rw cornerstone
```
    
#### Interactive Compile

```bash
sudo docker run -i -t -p 49000:9000 -v /vagrant/:/mnt/cornerstone:rw cornerstone compile /mnt/cornerstone/public
```

#### Daemon Mode Server

```bash
sudo docker run -d -p 49000:9000 -v /vagrant/:/mnt/cornerstone:rw cornerstone
```
