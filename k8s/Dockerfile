# STEP 1
FROM node:lts AS builder

WORKDIR /app

COPY . .

RUN yarn install
RUN yarn build

# STEP 2
FROM node:lts-alpine

WORKDIR /app

ENV NODE_ENV production

COPY --from=builder /app ./

CMD ["yarn", "start:prod"]