FROM nginx:stable

RUN apt-get update && apt-get install -y bash sed --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

COPY . /usr/share/nginx/html

RUN sed -i "s|__N8N_WEBHOOK_URL__|$N8N_WEBHOOK_URL|" /usr/share/nginx/html/script.js

EXPOSE 80