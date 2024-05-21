FROM mhart/alpine-node:16 AS builder
WORKDIR /app
COPY . .
RUN yarn install
RUN yarn build

FROM mhart/alpine-node:16
WORKDIR /app
COPY --from=builder /app/build ./build
RUN yarn global add serve
CMD ["serve", "-p", "80", "-s", "./build"]
