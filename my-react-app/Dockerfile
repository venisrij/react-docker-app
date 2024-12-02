FROM node:18-alpine

WORKDIR /my-react-app

# Step 2: Copy the content of the subfolder into the container’s working directory
COPY my-react-app/package.json ./package.json
COPY my-react-app/package-lock.json ./package-lock.json
COPY my-react-app/src ./src
COPY my-react-app/public ./public

RUN npm install

COPY . .
RUN npm run build

EXPOSE 3000
CMD ["npx", "serve", "-s", "build", "-l", "3000"]


