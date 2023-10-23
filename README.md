# DOCKER FOR NODE JS
- [DOCKER FOR NODE JS](#docker-for-node-js)
  - [Docker Compose Basics](#docker-compose-basics)
    - [how to check the docker version](#how-to-check-the-docker-version)
      - [docker version](#docker-version)
      - [docker compose version](#docker-compose-version)
    - [why compose](#why-compose)
      - [typical node server using a docker command](#typical-node-server-using-a-docker-command)
    - [compose file format](#compose-file-format)
      - [YAML](#yaml)
    - [docker compose CLI](#docker-compose-cli)
    - [Assignment](#assignment)
    - [](#)
    - [](#-1)
    - [](#-2)
    - [](#-3)
    - [](#-4)
    - [](#-5)

## Docker Compose Basics

### how to check the docker version

#### docker version
```bash
🐋 -> docker --version
```

#### docker compose version
```bash
🐋 -> docker-compose --version
```

### why compose

![Alt text](image.png)
#### typical node server using a docker command

![Alt text](image-1.png)

typing this command every time is not a good idea.

recommended way is to use docker compose

cli is node designed to run on production this is when orchestration comes in.

- docker swarm
- kubernetes

### compose file format
![Alt text](image-2.png)

![Alt text](image-3.png)


default `docker-compose.yml` file for docker-compose but we can use any file name with `-f` flag

```bash
🐋 -> docker-compose -f ["your file name"].yml up
```
#### YAML
![Alt text](image-4.png)

![Alt text](image-5.png)

![Alt text](image-6.png)

: for key/value pair
- for array


let's see a sample compose file

```yaml
version: '2.0'

services:
  web:
    image: sample-01
    build: .
    ports:
      - "3000:3000"
```


- version: version of compose file

![Alt text](image-8.png)

### docker compose CLI

![Alt text](image-9.png)

![Alt text](image-10.png)
![Alt text](image-11.png)
![Alt text](image-12.png)

`docker-compose up`

![Alt text](image-13.png)

to run the container in background

```bash
🐋 -> docker-compose up -d
```

![Alt text](image-14.png)

![Alt text](image-15.png)

![Alt text](image-16.png)

![Alt text](image-17.png)

![Alt text](image-19.png)


### Assignment
![Alt text](image-20.png)

```bash
# start the server
🐋 -> docker-compose up
# stop the server
🐋 -> docker-compose down
# start the server in background
🐋 -> docker-compose down
# check the status of the containers
🐋 -> docker-compose up -d
# check the status of the containers
🐋 -> docker-compose ps
# check the logs of the containers
🐋 -> docker-compose logs
```
```bash
> docker-compose up   
[+] Running 1/1
 ! web Warning                                                                                                                                                                                  7.1s 
[+] Building 141.4s (11/11) FINISHED                                                                                                                                                            docker:default
 => [web internal] load build definition from Dockerfile                                                                                                                                                  0.1s
 => => transferring dockerfile: 232B                                                                                                                                                                      0.0s
 => [web internal] load .dockerignore                                                                                                                                                                     0.1s
 => => transferring context: 455B                                                                                                                                                                         0.0s
 => [web internal] load metadata for docker.io/library/node:10-alpine                                                                                                                                     6.4s
 => [web auth] library/node:pull token for registry-1.docker.io                                                                                                                                           0.0s
 => [web 1/5] FROM docker.io/library/node:10-alpine@sha256:dc98dac24efd4254f75976c40bce46944697a110d06ce7fa47e7268470cf2e28                                                                              85.8s
 => => resolve docker.io/library/node:10-alpine@sha256:dc98dac24efd4254f75976c40bce46944697a110d06ce7fa47e7268470cf2e28                                                                                   0.1s
 => => sha256:dc98dac24efd4254f75976c40bce46944697a110d06ce7fa47e7268470cf2e28 1.65kB / 1.65kB                                                                                                            0.0s
 => => sha256:02767d92553e465bf51e0bd661074f2e70bd575c4a69a0d610aa6e78fd20a9bf 1.16kB / 1.16kB                                                                                                            0.0s
 => => sha256:aa67ba258e1877ed6ec455a7f4cc69e25cf0f0b027a7f6f3c63a8eca2c8a440c 6.73kB / 6.73kB                                                                                                            0.0s
 => => sha256:ddad3d7c1e96adf9153f8921a7c9790f880a390163df453be1566e9ef0d546e0 2.82MB / 2.82MB                                                                                                           18.8s
 => => sha256:de915e575d22c7e33c83fddaf7aee0672e5d6a67e598a26fe0b30c7022f53cdd 22.21MB / 22.21MB                                                                                                         81.9s
 => => sha256:7150aa69525b95f82b3df6a61a002f82382b2f3ea8ce51b9000b965f7476a5cc 2.35MB / 2.35MB                                                                                                           10.3s
 => => sha256:d7aa47be044e5a988e3e7f204e2e28cb9f070daa32ed081072ad6d5bf6c085d1 280B / 280B                                                                                                               15.1s
 => => extracting sha256:ddad3d7c1e96adf9153f8921a7c9790f880a390163df453be1566e9ef0d546e0                                                                                                                 0.2s
 => => extracting sha256:de915e575d22c7e33c83fddaf7aee0672e5d6a67e598a26fe0b30c7022f53cdd                                                                                                                 3.2s
 => => extracting sha256:7150aa69525b95f82b3df6a61a002f82382b2f3ea8ce51b9000b965f7476a5cc                                                                                                                 0.1s
 => => extracting sha256:d7aa47be044e5a988e3e7f204e2e28cb9f070daa32ed081072ad6d5bf6c085d1                                                                                                                 0.0s
 => [web internal] load build context                                                                                                                                                                     0.6s
 => => transferring context: 15.15MB                                                                                                                                                                      0.5s
 => [web 2/5] WORKDIR /usr/src/app                                                                                                                                                                        0.2s
 => [web 3/5] COPY package.json package-lock.json* ./                                                                                                                                                     0.1s
 => [web 4/5] RUN npm install && npm cache clean --force                                                                                                                                                 45.7s
 => [web 5/5] COPY . .                                                                                                                                                                                    0.1s
 => [web] exporting to image                                                                                                                                                                              1.9s
 => => exporting layers                                                                                                                                                                                   1.7s
 => => writing image sha256:0120acb63c9452adb5287b86f42db7dbdabd3aba26f71d4e6bc4ab3f66d79d09                                                                                                              0.1s
 => => naming to docker.io/library/sample-02                                                                                                                                                              0.1s
[+] Running 2/2
 ✔ Network sample-02_default  Created                                                                                                                                                                     0.5s 
 ✔ Container sample-02-web-1  Created                                                                                                                                                                     1.1s 
Attaching to sample-02-web-1
sample-02-web-1  | GET / 200 63.908 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 200 6.647 ms - 119
sample-02-web-1  | GET /images/picard7.gif 200 1.049 ms - 4572535
sample-02-web-1  | GET /favicon.ico 404 11.558 ms - 983
sample-02-web-1  | GET /mockServiceWorker.js 404 4.645 ms - 983
sample-02-web-1  | GET / 200 6.015 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.786 ms - -
sample-02-web-1  | GET /images/picard8.gif 200 1.016 ms - 1696869
sample-02-web-1  | GET /mockServiceWorker.js 404 5.021 ms - 983
sample-02-web-1  | GET / 200 4.679 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.680 ms - -
sample-02-web-1  | GET /images/picard5.gif 200 0.983 ms - 1078088
sample-02-web-1  | GET /mockServiceWorker.js 404 8.134 ms - 983
sample-02-web-1  | GET / 200 3.270 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.466 ms - -
sample-02-web-1  | GET /images/picard3.gif 200 0.936 ms - 961196
sample-02-web-1  | GET /mockServiceWorker.js 404 3.814 ms - 983
sample-02-web-1  | GET / 200 3.137 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 1.002 ms - -
sample-02-web-1  | GET /images/picard0.gif 200 1.277 ms - 2328735
sample-02-web-1  | GET /mockServiceWorker.js 404 8.136 ms - 983
sample-02-web-1  | GET / 200 2.739 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.597 ms - -
sample-02-web-1  | GET /images/picard6.gif 200 1.145 ms - 899094
sample-02-web-1  | GET /mockServiceWorker.js 404 3.102 ms - 983
sample-02-web-1  | GET / 304 6.149 ms - -
sample-02-web-1  | GET /stylesheets/style.css 304 0.629 ms - -
sample-02-web-1  | GET /images/picard6.gif 304 1.047 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.958 ms - 983
sample-02-web-1  | GET / 200 3.557 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.500 ms - -
sample-02-web-1  | GET /images/picard0.gif 304 0.443 ms - -
sample-02-web-1  | GET / 200 4.231 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.668 ms - -
sample-02-web-1  | GET /images/picard3.gif 304 0.586 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.425 ms - 983
sample-02-web-1  | GET / 200 3.810 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.559 ms - -
sample-02-web-1  | GET /images/picard1.gif 200 1.492 ms - 417700
sample-02-web-1  | GET /mockServiceWorker.js 404 8.117 ms - 983
sample-02-web-1  | GET / 200 4.432 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.419 ms - -
sample-02-web-1  | GET /images/picard0.gif 304 0.387 ms - -
sample-02-web-1  | GET / 200 2.572 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.393 ms - -
sample-02-web-1  | GET /images/picard8.gif 304 0.621 ms - -
sample-02-web-1  | GET / 304 4.445 ms - -
sample-02-web-1  | GET /stylesheets/style.css 304 0.358 ms - -
sample-02-web-1  | GET /images/picard8.gif 304 0.480 ms - -
sample-02-web-1  | GET / 200 4.526 ms - 299
sample-02-web-1  | GET /mockServiceWorker.js 404 7.427 ms - 983
sample-02-web-1  | GET /stylesheets/style.css 304 0.525 ms - -
sample-02-web-1  | GET /images/picard1.gif 304 0.585 ms - -
sample-02-web-1  | GET / 200 3.113 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.679 ms - -
sample-02-web-1  | GET /images/picard4.gif 200 0.937 ms - 368310
sample-02-web-1  | GET /mockServiceWorker.js 404 4.870 ms - 983
Gracefully stopping... (press Ctrl+C again to force)
Aborting on container exit...
[+] Stopping 1/1
 ✔ Container sample-02-web-1  Stopped                                                                                                                                                                     0.4s 
canceled
⬢  sample-02 ⚡ main ◉ 
> docker-compose down
[+] Running 2/2
 ✔ Container sample-02-web-1  Removed                                                                                                                                                                     0.0s 
 ✔ Network sample-02_default  Removed                                                                                                                                                                     0.3s 
⬢  sample-02 ⚡ main ◉ 
> docker-compose up -d
[+] Building 0.0s (0/0)                                                                                                                                                                         docker:default
[+] Running 2/2
 ✔ Network sample-02_default  Created                                                                                                                                                                     0.1s 
 ✔ Container sample-02-web-1  Started                                                                                                                                                                     0.1s 
⬢  sample-02 ⚡ main ◉ 
> docker-compose ps   
NAME              IMAGE       COMMAND                                 SERVICE   CREATED          STATUS          PORTS
sample-02-web-1   sample-02   "docker-entrypoint.sh node ./bin/www"   web       14 seconds ago   Up 13 seconds   0.0.0.0:3000->3000/tcp
⬢  sample-02 ⚡ main ◉ 
> docker-compose logs
⬢  sample-02 ⚡ main ◉ 
```

![Alt text](image-21.png)


```shell
docker-compose exec web sh
> docker-compose exec web sh
/usr/src/app # ls
app.js             bin                node_modules       package-lock.json  package.json       public             routes             views
/usr/src/app # curl localhost
sh: curl: not found
/usr/src/app # sudo apt install curl
sh: sudo: not found
/usr/src/app # apt install curl
sh: apt: not found
/usr/src/app # exit

```
so curl is not installed 

let's add this to the docker file

![Alt text](image-22.png)

updated docker file

```dockerfile
FROM node:10-alpine

EXPOSE 3000

WORKDIR /usr/src/app

COPY package.json package-lock.json* ./ 

RUN npm install && npm cache clean --force
RUN apk add --update curl
COPY . .

CMD [ "node", "./bin/www" ]

```

let's rerun the servi

```shell
docker-compose up -d
> docker-compose up -d
[+] Building 0.0s (0/0)                                                                                                                                                                         docker:default
[+] Running 2/2
 ✔ Network sample-02_default  Created                                                                                                                                                                     0.0s 
 ✔ Container sample-02-web-1  Started                                                                                                                                                                     0.0s 

```
notice we didn't rebuild the images 

let's force docker to rebuild the image

```shell
docker-compose up -d --build
> docker-compose up -d --build
[+] Building 34.6s (12/12) FINISHED                                                                                                                                                             docker:default
 => [web internal] load .dockerignore                                                                                                                                                                     0.0s
 => => transferring context: 455B                                                                                                                                                                         0.0s 
 => [web internal] load build definition from Dockerfile                                                                                                                                                  0.0s 
 => => transferring dockerfile: 257B                                                                                                                                                                      0.0s 
 => [web internal] load metadata for docker.io/library/node:10-alpine                                                                                                                                    12.1s 
 => [web auth] library/node:pull token for registry-1.docker.io                                                                                                                                           0.0s
 => [web 1/6] FROM docker.io/library/node:10-alpine@sha256:dc98dac24efd4254f75976c40bce46944697a110d06ce7fa47e7268470cf2e28                                                                               0.0s
 => [web internal] load build context                                                                                                                                                                     0.0s 
 => => transferring context: 1.11kB                                                                                                                                                                       0.0s 
 => CACHED [web 2/6] WORKDIR /usr/src/app                                                                                                                                                                 0.0s
 => CACHED [web 3/6] COPY package.json package-lock.json* ./                                                                                                                                              0.0s 
 => CACHED [web 4/6] RUN npm install && npm cache clean --force                                                                                                                                           0.0s 
 => [web 5/6] RUN apk add --update curl                                                                                                                                                                  22.1s 
 => [web 6/6] COPY . .                                                                                                                                                                                    0.1s
 => [web] exporting to image                                                                                                                                                                              0.1s
 => => exporting layers                                                                                                                                                                                   0.1s 
 => => writing image sha256:9b107d56e599b8b2b39815e4f72c2adf441a79bbc6570ce0add72f9a55dcb78e                                                                                                              0.0s 
 => => naming to docker.io/library/sample-02                                                                                                                                                              0.0s 
[+] Running 1/1
 ✔ Container sample-02-web-1  Started                                                                                                                                                                     0.6s 

```

let's try agin

```shell
docker-compose exec web sh
> docker-compose exec web sh  
/usr/src/app # curl localhost
curl: (7) Failed to connect to localhost port 80 after 0 ms: Connection refused
/usr/src/app # curl http://localhost:3000
<!DOCTYPE html>
<html>
  <head>
    <title>Node.js Express App</title>
    <link rel='stylesheet' href='/stylesheets/style.css' />
  </head>
  <body>
    <h1>Node.js Express App</h1>
<p>It Worked!  Enjoy a random Captain's gif</p>

<img src="/images/picard2.gif" />

  </body>
</html>
/usr/src/app #
/usr/src/app # exit


```

now curl is installed and our command worked

![Alt text](image-23.png)

![Alt text](image-24.png)

![Alt text](image-25.png)


logs output

```shell
docker-compose logs -f web
> docker-compose logs -f web 
sample-02-web-1  | GET / 200 79.012 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 200 5.962 ms - 119
sample-02-web-1  | GET /images/picard8.gif 304 1.249 ms - -
sample-02-web-1  | GET /favicon.ico - - ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.310 ms - 983
sample-02-web-1  | GET / 200 3.355 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.424 ms - -
sample-02-web-1  | GET /images/picard4.gif 304 0.642 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.930 ms - 983
sample-02-web-1  | GET / 304 5.750 ms - -
sample-02-web-1  | GET /stylesheets/style.css 304 0.357 ms - -
sample-02-web-1  | GET /images/picard4.gif 304 0.443 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.614 ms - 983
sample-02-web-1  | GET / 200 3.013 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.463 ms - -
sample-02-web-1  | GET /images/picard3.gif 304 0.397 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.129 ms - 983
sample-02-web-1  | GET / 200 2.982 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.479 ms - -
sample-02-web-1  | GET /images/picard0.gif 304 0.629 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 8.033 ms - 983
sample-02-web-1  | GET / 200 3.203 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.602 ms - -
sample-02-web-1  | GET /images/picard8.gif 304 0.491 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.768 ms - 983
sample-02-web-1  | GET / 200 5.160 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.604 ms - -
sample-02-web-1  | GET /images/picard1.gif 304 0.686 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.208 ms - 983
sample-02-web-1  | GET / 200 4.009 ms - 299
sample-02-web-1  | GET /stylesheets/style.css 304 0.434 ms - -
sample-02-web-1  | GET /images/picard8.gif 304 0.530 ms - -
sample-02-web-1  | GET /mockServiceWorker.js 404 3.368 ms - 983
canceled

```
### 
### 
###  
###  
### 
### 