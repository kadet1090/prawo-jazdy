FROM ubuntu:24.04

RUN apt update && apt install -y nodejs npm

WORKDIR /root
COPY . .
RUN npm ci
RUN npm run build

CMD ["npm", "run", "start"]