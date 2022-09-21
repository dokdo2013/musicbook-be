FROM node:lts AS builder

WORKDIR /app

COPY . /app

RUN yarn install
RUN yarn build

FROM node:lts-alphine

WORKDIR /app

COPY --from=builder /app ./

CMD ["npm", "run", "start:prod"]