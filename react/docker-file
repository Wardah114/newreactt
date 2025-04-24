# Build Phase
FROM node:20 AS builder
WORKDIR /app
COPY . .
RUN npm install && npm run build

# Serve via NGINX
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
