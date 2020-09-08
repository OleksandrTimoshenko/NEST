FROM node:12.13-alpine As development
WORKDIR /usr/src/app
RUN apk update && apk add bash
COPY ./package.json ./
COPY ./wait-for-it.sh ./wait-for-it.sh
RUN chmod +x ./wait-for-it.sh
CMD ["./wait-for-it.sh", "instamiligram_db:5432"]
RUN npm install
COPY . .
RUN npm run build
CMD ["node", "dist/main"]