FROM --platform=linux/amd64 node:latest
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .
EXPOSE 3000/tcp
CMD ["npm", "start"]