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

);

CREATE TABLE historial_clinico(

    id INT PRIMARY KEY AUTO_INCREMENT,
    mascota_id INT,
    veterinario_id INT,
    FOREIGN KEY (mascota_id) REFERENCES mascotas(id),
    FOREIGN KEY (veterinario_id) REFERENCES veterinarios(id),
    fecha_de_registro DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    descripcion VARCHAR(250) NOT NULL

);


INSERT INTO duenos (id,nombre,apellido,telefono,direccion) VALUES
(1,'Ash', 'Ketchup', 45236848, 'Pueblo paleta'),
(2,'Gary', 'Oak', 45236040, 'Pueblo paleta'),
(3,'Misty', 'Kasumi', 45236041, 'ciudad Celeste');

USE veterinaria_patitas_felices;

INSERT INTO mascotas (nombre,especie, fecha_de_nacimiento,dueno_id) VALUES 
('Pikachu','Electrico', '1996-02-27', 1),
('Arcanine','Fuego', '1996-04-27', 2),
('Starmie', 'Agua', '1996-03-27',3)

USE veterinaria_patitas_felices;

INSERT INTO veterinarios (nombre,apellido, matricula, especialidad) VALUES 
('Profesor','Oak', '4501', 'Iniciales'),
('Profesor','Abedul', '4502', 'Aventura');
