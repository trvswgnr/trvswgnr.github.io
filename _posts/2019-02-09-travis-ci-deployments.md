---
layout: post
title: "Travis CI Automated Build & Deployment"
permalink: /travis-ci/
categories: devops

---

<small>*__NOTE__: Always use travis-ci.com, not travis-ci.org (deprecated)*</small>

Install Travis CI Command Line Tool
```shell
gem install travis # (requires Ruby 1.9.3 or higher, check with ruby -v)
```

Login with GitHub account that's been authorized with Travis CI
```shell
travis login --com
```

```shell
ssh-keygen -t rsa -b 4096 -C 'build@travis-ci.org' -f ~./.ssh/deploy_rsa
```

Encrypt the ssh key and add to Travis CI Environment variables
```shell
travis encrypt-file ~/.ssh/deploy_rsa --add --com
```

Make sure that target directory exists on server and create it if it doesn't with FTP or SSH, otherwise `rsync` will generate an error since it can't create the parent directories.

## Configuration Files:
<script src="https://gist.github.com/trvswgnr/4973a29408fcb51b7a2b9155d0994bfd.js"></script>
