FROM node:18 AS builder
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app

FROM node:18-alpine as runner
WORKDIR /app
COPY --from=builder /app .
EXPOSE 3000
CMD ["node", "app.js"]