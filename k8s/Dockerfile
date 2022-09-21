FROM node:lts AS builder

COPY . /app

WORKDIR /app

RUN yarn install
RUN yarn build

COPY --from=builder /app ./

CMD ["npm", "run", "start:prod"]