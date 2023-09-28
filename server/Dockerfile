
# Utilizamos la imagen base de php:apache-bullseye
FROM node:18-alpine

# Establecemos el directorio de trabajo
WORKDIR /app

COPY . .

# Exponemos el puerto 81. Este puerto debe ser el mismo que se utiliza para crear el servidor y, al crear el contenedor, cuando hacemos el mapeo de puertos, el puerto del contenedor debe ser igual al puerto expuesto aquí.
EXPOSE 81

RUN npm install

CMD ["npm", "run", "dev"]