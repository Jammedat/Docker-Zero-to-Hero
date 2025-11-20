a. Create a docker network named as blog on App Server 3 in Stratos DC.


b. Configure it to use macvlan drivers.


c. Set it to use subnet 10.10.1.0/24 and iprange 10.10.1.0/24

## Solution

docker network create \
  --driver macvlan \
  --subnet=10.10.1.0/24 \
  --ip-range=10.10.1.0/22 \
  blog

You can inspect the network as:
` docker network inspect blog `
