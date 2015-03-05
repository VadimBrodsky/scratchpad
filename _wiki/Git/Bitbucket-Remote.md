# Bitbucket Remote

Adding Remote Bitbucket Server to Local Git Repo

``` bash
cd /path/to/my/repo
git remote add origin git@bitbucket.org:CrankWorksVB/test2.git
git push -u origin --all # pushes up the repo and its refs for the first time
git push -u origin --tags # pushes up any tags
```