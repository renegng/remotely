# Remotely
CMS para la Asistencia Remota

Remotely es una plataforma personalizable orientada a la atención remota de personas mujeres que han experimentado algún tipo de violencia.

Remotely tiene por base el código fuente de Contact-Os, el cual es la base para las plataformas 126 Te Orienta en El Salvador y Conecta en Honduras.

<p align="center"><img src="app/static/images/manifest/remotely-15.svg" width="512"/></p>

# Requerimientos

Remotely se encuentra empaquetado como un contenedor DOCKER y necesita de un administrador de contenedores como DOCKER, KUBERNETES o similar.

Remotely se encuentra desarrollado utilizando las siguientes tecnologías:
- Docker 20.10.10
- Python 3.8
- Python pip 21.2.4
- Flask 2.0.1
- Nginx 1.14.0 y Gunicorn 20.1.0
- SocketIO 3.1.0, Flask-SocketIO 5.1.1 y SimplePeer 9.7
- Elasticsearch 7.15.2
- MySQL 8.0 o PostgreSQL 14.1
- NodeJS 14.17.6
- React 17.0
- Redux 5.0
- npm 6.14.15
- librerías npm:
    - webpack@5
    - css-loader
    - sass-loader
    - node-sass
    - extract-loader
    - file-loader
    - babel-core 
    - babel-loader
    - material-components-web

# Pasos de instalación

En una consola de comandos, es necesario ejecutar los siguientes comandos:

1 - Instalar Docker (comandos para Ubuntu):

    ~: sudo apt-get remove docker docker-engine docker.io containerd runc
    ~: sudo apt-get update
    ~: sudo apt-get install ca-certificates curl gnupg sb-release
    ~: curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    ~: echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    ~: $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ~: sudo apt-get update
    ~: sudo apt-get install docker-ce docker-ce-cli containerd.io

    Verificar que la instalación de Docker fue exitosa ejecutando el siguiente comando:

    ~: sudo docker run hello-world
    ~: docker version

2 -  Instalar la plataforma, ejecutando el siguiente comando desde la carpeta raíz de este código donde se encuentra el archivo llamado docker-compose.yml:

    ~: docker-compose up -d --build

3 - Abrir una ventana de un navegador como Google Chrome, Mozilla Firefox o Microsoft Edge y acceder a la siguiente URL:

    - https://localhost en caso se ejecute localmente o con acceso local al servidor o 
    - https://IP_PUBLICA_O_DOMINIO en donde la palabra IP_PUBLICA se reemplaza por los números de la ip pública que se posee o por el dominio adquirido.

# Autores

Nidia Hidalgo - Especialista Lider, División de Género y Diversidad, BID.
Dinys Luciano - Consultora Experta en Violencia Contra las Mujeres.
René Navarrete - Consultor Experto en Tecnologia.
