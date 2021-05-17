### Installation instructions

**Node.js v16.x**:

```sh
# Using Ubuntu
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt-get install -y nodejs

# Using Debian, as root
curl -fsSL https://deb.nodesource.com/setup_16.x | bash -
apt-get install -y nodejs
```

**Node.js v15.x**:

```sh
# Using Ubuntu
curl -fsSL https://deb.nodesource.com/setup_15.x | sudo -E bash -
sudo apt-get install -y nodejs

# Using Debian, as root
curl -fsSL https://deb.nodesource.com/setup_15.x | bash -
apt-get install -y nodejs
```

**Node.js v14.x**:

```sh
# Using Ubuntu
curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs

# Using Debian, as root
curl -fsSL https://deb.nodesource.com/setup_14.x | bash -
apt-get install -y nodejs
```

# install
```
npm install
hexo init blog
cd blog
npm install hexo-feed --save-dev
npm install hexo-asset --save
npm install hexo-generator-json-content --save
npm install hexo-generator-sitemap --save
```
# post new 
```
hexo new "xxx"
hexo g
hexo s
```
# top
```
npm uninstall hexo-generator-index --save
npm install hexo-generator-index-pin-top --save
-----------
---
title: Hexo
categories: 
tags:
top: 10
---
```
## onekey deploy to heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?template=https://github.com/teasiu/blog/tree/main)
