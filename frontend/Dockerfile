# ============================
# STAGE 1: Build Angular App
# ============================
FROM node:18 AS build

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the full Angular project
COPY . .

# Build the Angular app for production
RUN npm run build

# ============================
# STAGE 2: Serve with Nginx
# ============================
FROM nginx:alpine

# Copy built Angular files from Stage 1
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

# Copy a default nginx config (optional if SPA routing required)
# COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

