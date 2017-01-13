# Fork of Consul Official Image Build on Debian

There are several pieces that are used to build this image:

* We start with an Debian base image and add CA certificates in order to reach
  the HashiCorp releases server. These are useful to leave in the image so that
  the container can access Atlas features as well.
* For set container timezone, use the TIMEZONE environment variable. The list of 
  valid time zone can found in: https://en.wikipedia.org/wiki/List_of_tz_database_time_zones 
* Official HashiCorp builds of some base utilities are then included in the
  image by pulling a release of docker-base. This includes dumb-init and gosu.
  See https://github.com/hashicorp/docker-base for more details.
* Finally a specific Consul build is fetched and the rest of the Consul-specific
  configuration happens according to the Dockerfile.

See https://hub.docker.com/_/consul/ for more details
