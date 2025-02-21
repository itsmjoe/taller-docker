# Taller 1: Introducción a Docker

## Descripción
En este taller, aprenderás los conceptos básicos de Docker, una plataforma de contenedorización que permite a los desarrolladores empaquetar aplicaciones y sus dependencias en contenedores portátiles.

## Objetivos
- Comprender qué es Docker y sus beneficios.
- Instalar Docker en tu máquina.
- Ejecutar tus primeros comandos de Docker.
- Crear y gestionar contenedores Docker.

## Requisitos
Tener una máquina virtual o instancia en cualquier proveedor de nube como Google Cloud, Azure, Amazon Web Services (AWS) o Digital Ocean, o bien una máquina virtual local. En este taller utilizaremos una máquina virtual alojada en AWS con sistema operativo linux, para ser mas específicos Ubuntu 24.04 LTS.

## Contenidos

### 1. ¿Qué es Docker?
Docker es una plataforma que permite a los desarrolladores empaquetar aplicaciones y sus dependencias en contenedores, que son entornos aislados y portátiles. Esto facilita la distribución y ejecución de aplicaciones en diferentes entornos sin preocuparse por las inconsistencias.

### 2. Instalación de Docker

Sigue las instrucciones oficiales para instalar Docker en tu sistema operativo:
- [Instalación en Windows](https://docs.docker.com/docker-for-windows/install/)
- [Instalación en macOS](https://docs.docker.com/docker-for-mac/install/)
- [Instalación en Linux](https://docs.docker.com/engine/install/)

#### Instalación en nuestra máquina virtual

1. **Conectarse a la máquina virtual**
    - Abre una terminal en tu máquina local.
    - Conéctate a tu máquina virtual usando SSH:
      ```sh
      ssh usuario@direccion-ip
      ```

2. **Actualizar los paquetes**
    - Una vez conectado a la máquina virtual, como usuario root, actualiza la lista de paquetes:
      ```sh
      sudo apt-get update
      ```

3. **Instalar Docker**
    - Instala Docker usando el siguiente comando:
      ```sh
      sudo apt-get install -y docker.io
      ```
    - Verifica la instalación de Docker:
      ```sh
      docker --version
      ```


### 3. Primeros Pasos con Docker
Una vez que Docker esté instalado, abre una terminal y ejecuta los siguientes comandos para verificar la instalación y familiarizarte con Docker:

1. **Descargar una imagen de Ubuntu**
    - Para descargar una imagen de Ubuntu desde Docker Hub, ejecuta el siguiente comando:
        ```sh
        docker pull ubuntu:24.04
        ```
    Este comando descarga la imagen de Ubuntu versión 24.04 desde el repositorio de Docker Hub a tu máquina local. Aquí, `ubuntu` es el nombre de la imagen y `24.04` es el tag que especifica la versión de Ubuntu que deseas descargar.

2. **Iniciar un contenedor**
    - Para iniciar un contenedor con la imagen de Ubuntu descargada, usa el siguiente comando:
      ```sh
      docker run -it --name mi_ubuntu ubuntu
      ```
    - Este comando inicia un contenedor en modo interactivo con un terminal bash.

3. **Detener el contenedor**
    - Para detener el contenedor en ejecución, primero necesitas conocer el ID o nombre del contenedor. Si usaste el nombre `mi_ubuntu`, puedes detenerlo con:
      ```sh
      docker stop mi_ubuntu
      ```

4. **Eliminar el contenedor**
    - Para eliminar el contenedor detenido, usa el siguiente comando:
      ```sh
      docker rm mi_ubuntu
      ```
