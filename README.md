# rmf-web
using rmf and rmf-web in one docker container

get docker

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

`pnpm env use --global 16`

dependencies

`pnpm install` 

`cd rmf-web/packages/dashboard`

`source /ros_entrypoint.sh`

`echo ROS_DOMAIN_ID=9`

`pnpm start`

from the new host terminal window 

`docker exec -it rmf-web /bin/bash`

`source /ros_entrypoint.sh`

`echo ROS_DOMAIN_ID=9`

`ros2 launch rmf_demos_gz office.launch.xml server_uri:="http://localhost:8000/_internal"`

