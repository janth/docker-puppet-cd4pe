This is a elaborate way to get a docker hub image when access to internet is blocked (ie docker pull don't work)

To create:

```bash
docker pull puppet/puppet-dev-tools:gosu
docker save puppet/puppet-dev-tools:gosu > puppet_puppet-dev-tools_gosu.tar 
xz puppet_puppet-dev-tools_gosu.tar
# To avoid github.com's filesize limit of 100Mb:
split --bytes=$((90*1000**2 )) --numeric-suffixes puppet-dev-tools_gosu.tar.xz  puppet-dev-tools_gosu--part
```

of https://hub.docker.com/r/puppet/puppet-dev-tools/tags

To use:

```bash
git clone git@github.com:janth/docker-puppet-cd4pe.git
```

then

```bash
cat puppet-dev-tools_gosu--part0? > puppet-dev-tools_gosu.tar.xz
docker load puppet_cd4pe-beta_hv-2.tar.xz
```


enjoy
