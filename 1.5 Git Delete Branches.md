### Nautilus developers are actively working on one of the project repositories, /usr/src/kodekloudrepos/news. They were doing some testing and created few test branches, now they want to clean those test branches. Below are the requirements that have been shared with the DevOps team:



On Storage server in Stratos DC delete a branch named xfusioncorp_news from /usr/src/kodekloudrepos/news git repo.

```ruby
thor@jump_host ~$ ssh natasha@ststor01


The authenticity of host 'ststor01 (172.16.238.15)' can't be established.
ECDSA key fingerprint is SHA256:/SmMo4x/5QbwBKTZjObJsut3Qf4OjVI5Wlks7+mxlqA.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ststor01,172.16.238.15' (ECDSA) to the list of known hosts.
natasha@ststor01's password: 

[natasha@ststor01 ~]$ sudo su -

[root@ststor01 ~]# cd /usr/src/kodekloudrepos/news

[root@ststor01 news]# git branch -a
  master
* xfusioncorp_news
  remotes/origin/master

[root@ststor01 news]# git branch -d xfusioncorp_news
error: Cannot delete branch 'xfusioncorp_news' checked out at '/usr/src/kodekloudrepos/news'

[root@ststor01 news]# git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

[root@ststor01 news]# git branch -d xfusioncorp_news
Deleted branch xfusioncorp_news (was 9e3953a).

[root@ststor01 news]# git branch -a
* master
  remotes/origin/master
[root@ststor01 news]# 

```
