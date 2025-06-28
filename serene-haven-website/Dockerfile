FROM nginx:stable

# Declare the build argument.
ARG N8N_WEBHOOK_URL

# Install bash and sed
RUN apt-get update && apt-get install -y bash sed --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

# Copy your website files
COPY . /usr/share/nginx/html

# Perform the substitution
RUN sed -i "s|__N8N_WEBHOOK_URL__|$N8N_WEBHOOK_URL|" /usr/share/nginx/html/script.js

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]