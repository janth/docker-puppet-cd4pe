This is a elaborate way to get a docker hub image when access to internet is blocked (ie docker pull don't work)

To create:
docker pull puppet/puppet-dev-tools:gosu
docker save puppet/puppet-dev-tools:gosu > puppet_puppet-dev-tools_gosu.tar 
of https://hub.docker.com/r/puppet/puppet-dev-tools/tags

To use:
git clone git@github.com:janth/docker-puppet-cd4pe.git
or
wget 
then
docker load puppet_cd4pe-beta_hv-2.tar.xz
