FROM nginx

RUN apt-get update && \
    apt-get install -y --no-install-recommends python3 && \
    apt-get install -y procps

COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./default.conf /etc/nginx/conf.d/default.conf

RUN addgroup --system --gid 5000 devops     && \
    adduser --system --disabled-login --ingroup devops --no-create-home \
    --home /nonexistent --gecos "devops user" --shell /bin/false --uid 5000 devops

RUN chown -R 5000:0 /var/cache/nginx     && \
    chmod -R g+w /var/cache/nginx     && chown -R 5000:0 /etc/nginx     && chmod -R g+w /etc/nginx

USER devops
EXPOSE 8080
COPY index.html /usr/share/nginx/html



