---
title: "[Ubuntu] Anaconda(아나콘다) 설치 후 conda 명령어 시 sudo 사용하라는 issue - NotWritableError: The current user does not have write permissions to a required path. In general, it's not advisable to use 'sudo conda'."
date: 2021-03-15 10:56:01 -0400
tags: sudo conda
categories:
  - Anaconda
comments: true
toc: true

---

<br/>
(base) [Mon Mar 15 / 21:12:27]jsh-fw:~$ conda create -n jsh-fw

NotWritableError: The current user does not have write permissions to a required path.
<br/>
  path: /home/jsh-fw/.conda/envs/.conda_envs_dir_test
<br/>
  uid: 1000
<br/>
  gid: 1000
<br/>
<br/>
If you feel that permissions on this path are set incorrectly, you can manually
<br/>
change them by executing
<br/>
  $ sudo chown 1000:1000 /home/jsh-fw/.conda/envs/.conda_envs_dir_test
<br/>
In general, it's not advisable to use 'sudo conda'.
<br/>
(base) [Mon Mar 15 / 21:12:33]jsh-fw:~$

<br/>
다음과 같은 문제 발생 시 아래 명령어로 해결할 수 있다.
<br/>
`sudo chown -R $USER:$USER anaconda3`
