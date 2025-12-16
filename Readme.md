1.- CREATE DATABASE veterinaria_patitas_felices1;

2.- CREATE TABLE duenos (

	id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR (50) NOT NULL,
    apellido VARCHAR (50) NOT NULL,
    telefono VARCHAR (20) NOT NULL,
    direccion VARCHAR (100)

);

3.-CREATE TABLE mascotas (

    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR (50) NOT NULL,
    especie VARCHAR (30) NOT NULL,
    fecha_de_nacimiento DATE,
    dueno_id INT NOT NULL,
    FOREIGN KEY (dueno_id) REFERENCES duenos(id) 

);

4.- CREATE TABLE veterinarios (

	id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(50) NOT NULL,
    apellido VARCHAR(50) NOT NULL,
    matricula VARCHAR(20) NOT NULL UNIQUE,
    especialidad VARCHAR(50) NOT NULL

)

CREATE TABLE historial_clinico(

    id INT PRIMARY KEY AUTO_INCREMENT,
    mascota_id INT,
    veterinario_id INT,
    FOREIGN KEY (mascota_id) REFERENCES mascotas(id),
    FOREIGN KEY (veterinario_id) REFERENCES veterinarios(id),
    fecha_de_registro DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    descripcion VARCHAR(250) NOT NULL

);