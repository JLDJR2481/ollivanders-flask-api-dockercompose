# ollivanders-flask-api-dockercompose

Este repositorio es un repositorio donde solo se destacará el uso de docker-compose para arrancar dos contenedores: uno con la imagen creada por el Dockerfile y otro con la imagen oficial de mongo. Si deseas tener mas información, aquí tienes el [repositorio original](https://github.com/JLDJR2481/ollivanders-flask-api-rest)

Para utilizar este repositorio, sigue los siguientes pasos:

1. Crea un directorio y dirigete al mismo:

```cmd
mkdir ./<nombre-directorio>
cd <nombre-directorio>
```

2. Crea un entorno virtual para instalar las dependencias sin afectar a la maquina local:

```cmd
python -m venv venv
```

3. Clona este repositorio:

```cmd
git clone https://github.com/JLDJR2481/ollivanders-flask-api-dockercompose
```

4. Instala las dependencias y paquetes necesarios entrando al entorno virtual:

```cmd
source venv/Scripts/activate
pip3 install -r requirements.txt
```

5. Añade una URI con API de Mongo a un archivo .env:

```cmd
touch .env
```

En el archivo .env, añadimos una URI. Aquí tienes una URI de ejemplo:
URI = "mongodb+srv://username:password@database.API.mongodb.net/?retryWrites=true&w=majority"

Reemplaza username con el usuario con permisos en tu base de datos, password con la contraseña del mismo, database por el nombre de la base de datos (preferiblemente, ollivanders, aunque puede ser cualquiera) y API con la API que te proporciona MongoDB Atlas tras pedirla.

Más información sobre la API de Mongo [aquí](https://www.mongodb.com/docs/atlas/api/)

6. Creamos la imagen de Docker que contiene la aplicación para conectarla junto a un contenedor docker:

```cmd
docker build -t <nombre-imagen> .
```

Como recomendación, y para evitar tener que modificar el archivo de docker-compose.yml, se aconseja nombrar la imagen como ollivanders-flask.

7. Ejecutamos el docker-compose:

```cmd
docker-compose up
```

Si preferimos dejarlo en 2º plano, ejecutamos:

```cmd
docker-compose up -d
```

Tras ello, podemos interactuar con la aplicación junto al contenedor de MongoDB
