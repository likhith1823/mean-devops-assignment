# Stage 1 - Build Angular
FROM node:18 AS build
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npx ng build --configuration production


# Stage 2 - Serve with Nginx
FROM nginx:alpine

# Copy custom nginx config (for Angular routing fix)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy built Angular files
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
