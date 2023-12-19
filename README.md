# rmf-web
using rmf and rmf-web in one docker container 

start docker

`start-docker-host.sh rmf-web`

`cd /rmf-web/packages/dashboard`

`source /ros_entrypoint.sh`

`ROS_DOMAIN_ID=7`

`pnpm start`

goto jump0:

if not container exist get docker

`docker pull ghcr.io/open-rmf/rmf/rmf_demos:latest` 

`docker tag ghcr.io/open-rmf/rmf/rmf_demos:latest rmf:latest`

start docker with x11 gui support

`start-docker-host.sh rmf-web rmf:latest true`

adding rmf-web source

`curl -sL https://deb.nodesource.com/setup_16.x | bash -`

`apt-get update`

`apt-get install nodejs jq`

`pip3 install pipenv && npm config set unsafe-perm`

`git clone https://github.com/open-rmf/rmf-web.git`

`curl -fsSL https://get.pnpm.io/install.sh | bash -`

`source /root/.bashrc`

`cd /rmf-web`

`pnpm env use --global 16`

dependencies

`pnpm install` 

`cd /packages/dashboard`

`source /ros_entrypoint.sh`

`ROS_DOMAIN_ID=7`

`pnpm start`

jump0:

from the new host terminal window 

`docker exec -it rmf-web /bin/bash`

`source /ros_entrypoint.sh`

`ROS_DOMAIN_ID=7`

`ros2 launch rmf_demos_gz office.launch.xml server_uri:="http://localhost:8000/_internal"`

