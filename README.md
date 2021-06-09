docker build . -t 32518/nginx-devops:v1
docker scan 32518/nginx-devops:v1
docker push 32518/nginx-devops:v1

echo -n 'DevOps' | openssl base64