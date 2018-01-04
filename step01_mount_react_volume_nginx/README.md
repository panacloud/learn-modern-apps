Now we want to run the React app created in step00 and mounting it in a Nginx container.

To build static files:

npm run build

Then I installed Docker on my machine:

https://www.docker.com/community-edition

To learn about Docker read the first eight chapters of Docker Deep Dive by Nigel Poulton:

https://www.amazon.com/Docker-Deep-Dive-Nigel-Poulton/dp/1521822808/ref=sr_1_1

In order to run React app on Nginx I will use this image:

https://hub.docker.com/_/nginx/

https://blog.docker.com/2015/04/tips-for-deploying-nginx-official-image-with-docker/

Give the following command load the volume:

docker run --name step00-nginx -v $(pwd)/build:/usr/share/nginx/html:ro -p 8080:80 -d nginx

Open in the browser:

http://localhost:8080/

