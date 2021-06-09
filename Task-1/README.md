docker build . -t 32518/nginx-devops:d1
docker push 32518/nginx-devops:d1

echo -n 'DevOps' | openssl base64