---
layout: posts
title: "VS Code Remote SSH Permission Denied"
category: posts
---

`ssh {user}@{ip}` works, but VS Code remote SSH doesn't with the following error.

> Permission denied (publickey,password)

Simplest solution:

1. Add IdentityFile

`~/.ssh/config` file should look something like the following:

``
Host {ip}
  HostName {name}
  User {user}
  IdentityFile ~/.ssh/{file}
``