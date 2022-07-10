# cpanelplugins.com

<img src="https://raw.githubusercontent.com/cpanelplugins/cpanelplugins.com/master/plugins/screenshots/cpanel-plugins-homepage.png"></img>

CpanelPlugins is a github-hosted open-source collection of awesome cPanel plugins.

[![Netlify Status](https://api.netlify.com/api/v1/badges/17640f2a-1ce1-4f0e-8bac-4f920a8f7543/deploy-status)](https://app.netlify.com/sites/sweet-peony-734550/deploys)

## How to add a plugin

To add your plugin:

1. Fork this repo [cpanelplugins/cpanelplugins.com](https://github.com/cpanelplugins/cpanelplugins.com)
2. Add your plugin information to the plugins/plugins.yaml file
3. Make a pull request with the following title: ADD PLUGIN

NOTE: The plugin information shoud be in the following format:

```
- title: TODO
  description: Sample Code for cPanel Conf 2016
  screenshot: ./screenshots/todo.png
  repo: squareplanetdesign/cpanel_todo_plugin
  preview: https://documentation.cpanel.net/display/DD/Guide+to+cPanel+Plugins
  author: cpanelinc
  tags: todo, plugin, free
  platforms: strapi
```


## How to add a blog post

1. Fork this repo [cpanelplugins/cpanelplugins.com](https://github.com/cpanelplugins/cpanelplugins.com)
2. Create a directory with the date and title of the post (e.g. 2022-06-26-cpanelplugins.com-is-live)
3. Create index.md file inside it with the actual blog post
4. Add your information inside contributors/contributors.yaml file and profile picture to contributors/images
5. Make a pull request with the following title: ADD POST


NOTE: The blog post (index.md) file must contain the following information at the top:

```
---
title | slug | author | date | excerpt
---
```

for example:

```
---
title: CpanelPlugins.com Is live 🎉🎉🎉
slug: cpanel-plugins-is-live
author: [stefanpejcic]
date: 2021-06-26
excerpt: "CpanelPlugins.com website is published!"
---
```

---


TODO:

- add sitemap generator
- set white theme as default
- 
