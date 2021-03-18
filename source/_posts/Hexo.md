---
title: Hexo 安装配置
categories: Tool
tags: Hexo
abbrlink: 1b0927de
date: 2020-10-16 00:22:01
---
### 基础功能
  ```sh
  npm config set registry https://registry.npm.taobao.org
  npm install hexo-cli -g
  mkdir blog && cd blog
  hexo init
  npm install hexo-server --save
  npm install hexo-deployer-git --save
  ```

### 克隆source文件
  ```sh
  rm -rf source
  rm -rf scaffolds
  git clone git@github.com:yqi96/yqi96.github.io.git ./tmp
  cp -r tmp/.* . && rm -rf tmp
  ```

### 主题

  ```sh
  git clone https://github.com/tufu9441/maupassant-hexo.git themes/maupassant
  npm install hexo-renderer-pug --save
  npm install hexo-renderer-sass --save
  ```

### 页面显示

  ```sh
  npm install hexo-generator-index --save
  npm install hexo-generator-archive --save
  npm install hexo-generator-category --save
  npm install hexo-generator-tag --save
  npm install hexo-generator-search --save
  # npm install hexo-asset-image --save
  ```

### 唯一链接

  ```sh
  npm install hexo-abbrlink --save
  npm install https://github.com/foreveryang321/hexo-asset-image.git --save
  ```

### 备忘

  - 兼容[hexo-abbrlink](https://github.com/Rozbo/hexo-abbrlink)的[hexo-asset-image](https://github.com/foreveryang321/hexo-asset-image)

---

