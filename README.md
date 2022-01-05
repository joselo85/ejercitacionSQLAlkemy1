# Ejercitacion para el Modulo SQL Inicial Alkemy

1. Cree una tabla llamada CURSO con los atributos:
  1. Código de curso (clave primaria, entero no nulo)
  2. Nombre (varchar no nulo)
  3. Descripcion (varcha)
  4. Turno (varchar no nulo)
 `CREATE TABLE curso (codigo_de_curso INT NOT NULL, nombre VARCHAR(60) NOT NULL, descripcion VARCHAR(100), turno VARCHAR(40) NOT NULL, PRIMARY KEY(codigo_de_curso) )`
 
2. Agregue un campo “cupo” de tipo numérico
  `ALTER TABLE curso ADD cupo INT`
3. Inserte datos en la tabla:
  (101, “Algoritmos”,”Algoritmos y Estructuras de Datos”,”Mañana”,35)
  (102, “Matemática Discreta”,””,”Tarde”,30)
  `INSERT INTO curso (codigo_de_curso, nombre, descripcion, turno, cupo) VALUES (101, 'Algoritmos', 'Algoritmos y Estructuras de Datos', 'Mañana', 35)`
  `INSERT INTO curso (codigo_de_curso, nombre, descripcion, turno, cupo) VALUES (102, 'Matemática Discreta', '', 'Tarde', 30)`
  ![image](https://user-images.githubusercontent.com/74208929/148301485-3e53b88c-f412-4306-a0e5-e980da430b33.png)

4. Intente ingresar un registro con el nombre nulo y verifique que no funciona.
   `INSERT INTO curso (codigo_de_curso, nombre, descripcion, turno, cupo) VALUES (103, NULL, 'Algoritmos y Estructuras de Datos', 'Mañana', 35)`
   ![image](https://user-images.githubusercontent.com/74208929/148302941-86519f71-5955-4648-a9f0-a85efce2ab95.png)

5. Intente ingresar un registro con la clave primaria repetida y verifique que no funciona.
   `INSERT INTO curso (codigo_de_curso, nombre, descripcion, turno, cupo) VALUES (101, 'Algoritmos', 'Algoritmos y Estructuras de Datos', 'Mañana', 35)`
   ![image](https://user-images.githubusercontent.com/74208929/148303113-5f2f0bcc-263d-46c0-a1f9-55702a754400.png)

6. Actualice, para todos los cursos, el cupo en 25.
   `UPDATE curso set cupo=25`
   ![image](https://user-images.githubusercontent.com/74208929/148303326-5472d681-d3d2-4d52-a139-8ee34eaa863e.png)

7. Elimine el curso Algoritmos.
   `DELETE FROM curso WHERE nombre='Algoritmos'`
