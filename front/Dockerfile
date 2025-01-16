FROM docker.cui.pg.gda.pl/base/node:18

WORKDIR /docker/www

COPY package.json package-lock.json ./
RUN npm ci

COPY . .
RUN npm run build

CMD ["npm", "run", "start"]