# base
FROM node:18.11.0
# cria um diretório para o trabalho
WORKDIR /app
# copia para usar o cache
COPY package*.json ./
# fica após a cópia apenas dos packages para não rodar atoa
# pois é um processo pesado
RUN npm install
# passa o código para a imagem
COPY . .
# permite a porta ser acessada
EXPOSE 8080
# roda de fato
CMD ["node", "server.js"]
