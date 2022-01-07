# Ejercitacion para el Modulo SQL Inicial Alkemy

## Tema 1: Manipulacion

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
 
*** 
## Tema 2:
Consigna 3:

Cargue una captura de pantalla  de qué resultado se obtiene después de ejecutar:

`SELECT profesor.Apellido , curso.Nombre, curso.turno FROM profesor LEFT JOIN curso ON profesor.id = curso.PROFESOR_id;`

![image](https://user-images.githubusercontent.com/74208929/148616143-7fe6514d-25a7-4ffc-883f-dcbe23ef18b0.png)


***
## Tema 3: Queries
    
1. Nombre, apellido y fecha de nacimiento de todos los empleados, ordenado por fecha de nacimiento ascendente.

`SELECT nombre, apellido, fecha_nacimiento FROM profesor ORDER BY fecha_nacimiento`

3. Todos los profesores cuyo salario sea mayor o igual a 65000.

`SELECT * FROM profesor WHERE (salario >=65000)`

5. Todos los profesores que nacieron en la década del 80.

`SELECT * FROM profesor WHERE fecha_nacimiento BETWEEN '1980-01-01' AND '1989-12-31'`
 
`SELECT * FROM profesor WHERE (fecha_nacimiento > '1979-12-31' AND fecha_nacimiento < '1990-01-01')`

7. 5 registros

`SELECT * FROM profesor LIMIT 5`

9. Todos los profesores cuyo apellido inicie con la letra “P”

`SELECT * FROM profesor WHERE apellido LIKE '%P%'`

11. Los profesores que nacieron en la década del 80 y tienen un salario mayor a 80000
  
`SELECT * FROM profesor WHERE ((fecha_nacimiento BETWEEN '1980-01-01' AND '1989-12-31') AND (salario >= 80000))`
