---
layout: posts
title: "VS Code Remote SSH Permission Denied"
updated: 2021-06-26
category: posts
---

`ssh {user}@{ip}` works, but VS Code remote SSH doesn't.

``
Permission denied (publickey,password)
``

1. Add IdentityFile

``
Host {ip}
  HostName {name}
  User {user}
  IdentityFile ~/.ssh/{file}
``