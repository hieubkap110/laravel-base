FROM nginx:latest

# Update user in nginx.conf for non-Linux environments
RUN if [[ "$OSTYPE" == "darwin"* || "$OSTYPE" == "msys"* ]]; then sed -i 's/user  nginx;/user  root;/' /etc/nginx/nginx.conf; fi

COPY docker/nginx/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
