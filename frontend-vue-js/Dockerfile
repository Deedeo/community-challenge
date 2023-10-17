FROM node:lts-alpine AS build
WORKDIR /frontend-vue-js

# Install dependencies
COPY package.json .
COPY package-lock.json .
RUN npm ci

# Copy the application source
COPY . .
# Build vue
RUN npm run build



FROM nginx:stable-alpine

COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /frontend-vue-js /usr/share/nginx/html

EXPOSE 80