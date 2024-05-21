FROM node:16-alpine

RUN mkdir -p /usr/src/app

WORKDIR /usr

COPY . .


# Update package lists and install Python
RUN apk update && \
    apk add --no-cache python3 make g++

# Set Python 3 as the default Python version
RUN rm -f /usr/bin/python && \
    ln -s /usr/bin/python3 /usr/bin/python


RUN yarn install


EXPOSE 3000
CMD ["yarn","start", "migration:start"]