# TALLER BASE DE DATOS.

1. Lista el primer apellido de todos los empleados.

   ```sql
   SELECT apellido1 
   FROM empleado;
   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Salas     |
   | Sáez      |
   +-----------+
   13 rows in set (0,00 sec)
   
   ```

2. Lista el primer apellido de los empleados eliminando los apellidos que estén
    repetidos.

  ```sql
  SElECT DISTINCT apellido1 
  FROM empleado;
  +-----------+
  | apellido1 |
  +-----------+
  | Rivero    |
  | Salas     |
  | Rubio     |
  | Suárez    |
  | Loyola    |
  | Santana   |
  | Ruiz      |
  | Gómez     |
  | Flores    |
  | Herrera   |
  | Sáez      |
  +-----------+
  11 rows in set (0,00 sec)
  
  ```

3. Lista todas las columnas de la tabla empleado.

   ```sql
   SElECT codigo,nif,nombre,apellido1,apellido2,codigo_departamento 
   FROM empleado;
   +--------+-----------+--------------+-----------+-----------+---------------------+
   | codigo | nif       | nombre       | apellido1 | apellido2 | codigo_departamento |
   +--------+-----------+--------------+-----------+-----------+---------------------+
   |      1 | 32481596F | Aarón        | Rivero    | Gómez     |                   1 |
   |      2 | Y5575632D | Adela        | Salas     | Díaz      |                   2 |
   |      3 | R6970642B | Adolfo       | Rubio     | Flores    |                   3 |
   |      4 | 77705545E | Adrián       | Suárez    | NULL      |                   4 |
   |      5 | 17087203C | Marcos       | Loyola    | Méndez    |                   5 |
   |      6 | 38382980M | María        | Santana   | Moreno    |                   1 |
   |      7 | 80576669X | Pilar        | Ruiz      | NULL      |                   2 |
   |      8 | 71651431Z | Pepe         | Ruiz      | Santana   |                   3 |
   |      9 | 56399183D | Juan         | Gómez     | López     |                   2 |
   |     10 | 46384486H | Diego        | Flores    | Salas     |                   5 |
   |     11 | 67389283A | Marta        | Herrera   | Gil       |                   1 |
   |     12 | 41234836R | Irene        | Salas     | Flores    |                NULL |
   |     13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |                NULL |
   +--------+-----------+--------------+-----------+-----------+---------------------+
   13 rows in set (0,00 sec)
   
   ```

4. Lista el nombre y los apellidos de todos los empleados.

   ```sql
   SELECT nombre,apellido1,apellido2 
   FROM empleado;
   +--------------+-----------+-----------+
   | nombre       | apellido1 | apellido2 |
   +--------------+-----------+-----------+
   | Aarón        | Rivero    | Gómez     |
   | Adela        | Salas     | Díaz      |
   | Adolfo       | Rubio     | Flores    |
   | Adrián       | Suárez    | NULL      |
   | Marcos       | Loyola    | Méndez    |
   | María        | Santana   | Moreno    |
   | Pilar        | Ruiz      | NULL      |
   | Pepe         | Ruiz      | Santana   |
   | Juan         | Gómez     | López     |
   | Diego        | Flores    | Salas     |
   | Marta        | Herrera   | Gil       |
   | Irene        | Salas     | Flores    |
   | Juan Antonio | Sáez      | Guerrero  |
   +--------------+-----------+-----------+
   13 rows in set (0,00 sec)
   
   ```

5. Lista el identificador de los departamentos de los empleados que aparecen
    en la tabla empleado.

  ```sql
  SELECT codigo_departamento 
  FROM empleado;
  +---------------------+
  | codigo_departamento |
  +---------------------+
  |                   1 |
  |                   2 |
  |                   3 |
  |                   4 |
  |                   5 |
  |                   1 |
  |                   2 |
  |                   3 |
  |                   2 |
  |                   5 |
  |                   1 |
  |                NULL |
  |                NULL |
  +---------------------+
  13 rows in set (0,00 sec)
  
  ```

6. Lista el identificador de los departamentos de los empleados que aparecen
    en la tabla empleado, eliminando los identificadores que aparecen repetidos.

  ```sql
  SELECT DISTINCT codigo_departamento 
  FROM empleado;
  +---------------------+
  | codigo_departamento |
  +---------------------+
  |                   1 |
  |                   2 |
  |                   3 |
  |                   4 |
  |                   5 |
  |                NULL |
  +---------------------+
  6 rows in set (0,00 sec)
  
  ```

7. Lista el nombre y apellidos de los empleados en una única columna.

   ```sql
   SELECT CONCAT(nombre, ' ', apellido1,' ',apellido2) AS nombre_empleado
   FROM empleado;
   +-----------------------------+
   | nombre_empleado             |
   +-----------------------------+
   | Aarón Rivero Gómez          |
   | Adela Salas Díaz            |
   | Adolfo Rubio Flores         |
   | NULL                        |
   | Marcos Loyola Méndez        |
   | María Santana Moreno        |
   | NULL                        |
   | Pepe Ruiz Santana           |
   | Juan Gómez López            |
   | Diego Flores Salas          |
   | Marta Herrera Gil           |
   | Irene Salas Flores          |
   | Juan Antonio Sáez Guerrero  |
   +-----------------------------+
   13 rows in set (0,00 sec)
   
   ```

8. Lista el nombre y apellidos de los empleados en una única columna,
    convirtiendo todos los caracteres en mayúscula.

  ```sql
  SELECT UPPER(CONCAT(nombre,' ',apellido1,' ',apellido2)) AS nombre_empleado
  FROM empleado;
  +-----------------------------+
  | nombre_empleado             |
  +-----------------------------+
  | AARÓN RIVERO GÓMEZ          |
  | ADELA SALAS DÍAZ            |
  | ADOLFO RUBIO FLORES         |
  | NULL                        |
  | MARCOS LOYOLA MÉNDEZ        |
  | MARÍA SANTANA MORENO        |
  | NULL                        |
  | PEPE RUIZ SANTANA           |
  | JUAN GÓMEZ LÓPEZ            |
  | DIEGO FLORES SALAS          |
  | MARTA HERRERA GIL           |
  | IRENE SALAS FLORES          |
  | JUAN ANTONIO SÁEZ GUERRERO  |
  +-----------------------------+
  13 rows in set (0,00 sec)
  
  ```

9. Lista el nombre y apellidos de los empleados en una única columna,
    convirtiendo todos los caracteres en minúscula.

  ```sql
  SELECT LOWER(CONCAT(nombre,' ',apellido1,' ',apellido2)) AS nombre_empleados
  FROM empleado;
  +-----------------------------+
  | nombre_empleados            |
  +-----------------------------+
  | aarón rivero gómez          |
  | adela salas díaz            |
  | adolfo rubio flores         |
  | NULL                        |
  | marcos loyola méndez        |
  | maría santana moreno        |
  | NULL                        |
  | pepe ruiz santana           |
  | juan gómez lópez            |
  | diego flores salas          |
  | marta herrera gil           |
  | irene salas flores          |
  | juan antonio sáez guerrero  |
  +-----------------------------+
  13 rows in set (0,00 sec)
  
  ```

10. Lista el identificador de los empleados junto al nif, pero el nif deberá
    aparecer en dos columnas, una mostrará únicamente los dígitos del nif y la
    otra la letra.

    ```sql
    SELECT codigo, 
    SUBSTRING(nif, 1, LENGTH(nif) - 1) AS digitos_nif, 
    RIGHT(nif, 1) AS letra_nif
    FROM empleado;
    +--------+-------------+-----------+
    | codigo | digitos_nif | letra_nif |
    +--------+-------------+-----------+
    |      1 | 32481596    | F         |
    |      2 | Y5575632    | D         |
    |      3 | R6970642    | B         |
    |      4 | 77705545    | E         |
    |      5 | 17087203    | C         |
    |      6 | 38382980    | M         |
    |      7 | 80576669    | X         |
    |      8 | 71651431    | Z         |
    |      9 | 56399183    | D         |
    |     10 | 46384486    | H         |
    |     11 | 67389283    | A         |
    |     12 | 41234836    | R         |
    |     13 | 82635162    | B         |
    +--------+-------------+-----------+
    13 rows in set (0,00 sec)
    
    ```

11. Lista el nombre de cada departamento y el valor del presupuesto actual del
    que dispone. Para calcular este dato tendrá que restar al valor del
    presupuesto inicial (columna presupuesto) los gastos que se han generado
    (columna gastos). Tenga en cuenta que en algunos casos pueden existir
    valores negativos. Utilice un alias apropiado para la nueva columna columna
    que está calculando.

    ```sql
    SELECT nombre, (presupuesto - gasto) AS presupuesto 
    FROM departamento;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Desarrollo       |      114000 |
    | Sistemas         |      129000 |
    | Recursos Humanos |      255000 |
    | Contabilidad     |      107000 |
    | I+D              |       -5000 |
    | Proyectos        |           0 |
    | Publicidad       |       -1000 |
    +------------------+-------------+
    7 rows in set (0,00 sec)
    
    ```

12. Lista el nombre de los departamentos y el valor del presupuesto actual
    ordenado de forma ascendente.

    ```sql
    SELECT  nombre,presupuesto 
    FROM departamento
    ORDER BY presupuesto ASC; 
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Proyectos        |           0 |
    | Publicidad       |           0 |
    | Contabilidad     |      110000 |
    | Desarrollo       |      120000 |
    | Sistemas         |      150000 |
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    +------------------+-------------+
    7 rows in set (0,00 sec)
    
    ```

13. Lista el nombre de todos los departamentos ordenados de forma
    ascendente.

    ```sql
    SELECT  nombre
    FROM departamento
    ORDER BY nombre ASC; 
    +------------------+
    | nombre           |
    +------------------+
    | Contabilidad     |
    | Desarrollo       |
    | I+D              |
    | Proyectos        |
    | Publicidad       |
    | Recursos Humanos |
    | Sistemas         |
    +------------------+
    7 rows in set (0,00 sec)
    
    ```

14. Lista el nombre de todos los departamentos ordenados de forma
    descendente.

```sql
SELECT  nombre
FROM departamento
ORDER BY nombre DESC; 
+------------------+
| nombre           |
+------------------+
| Sistemas         |
| Recursos Humanos |
| Publicidad       |
| Proyectos        |
| I+D              |
| Desarrollo       |
| Contabilidad     |
+------------------+
7 rows in set (0,00 sec)

```

15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma
    alfabética tendiendo en cuenta en primer lugar sus apellidos y luego su
    nombre.

    ```sql
    SELECT apellido1, apellido2, nombre AS nombre 
    FROM empleado 
    ORDER BY apellido1 ASC, apellido2 ASC, nombre ASC;
    +-----------+-----------+--------------+
    | apellido1 | apellido2 | nombre       |
    +-----------+-----------+--------------+
    | Flores    | Salas     | Diego        |
    | Gómez     | López     | Juan         |
    | Herrera   | Gil       | Marta        |
    | Loyola    | Méndez    | Marcos       |
    | Rivero    | Gómez     | Aarón        |
    | Rubio     | Flores    | Adolfo       |
    | Ruiz      | NULL      | Pilar        |
    | Ruiz      | Santana   | Pepe         |
    | Sáez      | Guerrero  | Juan Antonio |
    | Salas     | Díaz      | Adela        |
    | Salas     | Flores    | Irene        |
    | Santana   | Moreno    | María        |
    | Suárez    | NULL      | Adrián       |
    +-----------+-----------+--------------+
    13 rows in set (0,00 sec)
    
    ```

16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos
    que tienen mayor presupuesto.

    ```sql
    SELECT nombre,presupuesto FROM departamento
    ORDER BY presupuesto DESC LIMIT 3;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | I+D              |      375000 |
    | Recursos Humanos |      280000 |
    | Sistemas         |      150000 |
    +------------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos
    que tienen menor presupuesto.

    ```sql
    SELECT nombre,presupuesto 
    FROM departamento ORDER BY presupuesto ASC  LIMIT 3;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Proyectos    |           0 |
    | Publicidad   |           0 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que
    tienen mayor gasto.

    ```sql
    SELECT nombre, presupuesto 
    FROM departamento 
    ORDER BY presupuesto DESC 
    LIMIT 3;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | I+D              |      375000 |
    | Recursos Humanos |      280000 |
    | Sistemas         |      150000 |
    +------------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que
    tienen menor gasto.

    ```sql
    SELECT nombre, presupuesto  
    FROM departamento  
    ORDER BY presupuesto ASC  LIMIT 3;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Proyectos    |           0 |
    | Publicidad   |           0 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado. La
    tercera fila se debe incluir en la respuesta. La respuesta debe incluir todas las
    columnas de la tabla empleado.

    ```sql
    SELECT codigo,nif,nombre,apellido1,apellido2,codigo_departamento 
    FROM empleado
    LIMIT 5 OFFSET 2;
    +--------+-----------+---------+-----------+-----------+---------------------+
    | codigo | nif       | nombre  | apellido1 | apellido2 | codigo_departamento |
    +--------+-----------+---------+-----------+-----------+---------------------+
    |      3 | R6970642B | Adolfo  | Rubio     | Flores    |                   3 |
    |      4 | 77705545E | Adrián  | Suárez    | NULL      |                   4 |
    |      5 | 17087203C | Marcos  | Loyola    | Méndez    |                   5 |
    |      6 | 38382980M | María   | Santana   | Moreno    |                   1 |
    |      7 | 80576669X | Pilar   | Ruiz      | NULL      |                   2 |
    +--------+-----------+---------+-----------+-----------+---------------------+
    5 rows in set (0,00 sec)
    
    ```

21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de
    aquellos que tienen un presupuesto mayor o igual a 150000 euros.

    ```sql
    SELECT nombre,presupuesto FROM departamento
    WHERE presupuesto >=150000;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Sistemas         |      150000 |
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    +------------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

22. Devuelve una lista con el nombre de los departamentos y el gasto, de
    aquellos que tienen menos de 5000 euros de gastos.

    ```sql
    SELECT nombre,gasto 
    FROM departamento 
    WHERE gasto <5000;
    +--------------+-------+
    | nombre       | gasto |
    +--------------+-------+
    | Contabilidad |  3000 |
    | Proyectos    |     0 |
    | Publicidad   |  1000 |
    +--------------+-------+
    3 rows in set (0,00 sec)
    
    ```

23. Devuelve una lista con el nombre de los departamentos y el presupuesto, de
    aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin
    utilizar el operador BETWEEN.

    ```sql
    SELECT nombre,presupuesto FROM departamento
    WHERE presupuesto >=100000 AND presupuesto <=200000;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Desarrollo   |      120000 |
    | Sistemas     |      150000 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

24. Devuelve una lista con el nombre de los departamentos que no tienen un
    presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.

    ```sql
    SELECT nombre,presupuesto FROM departamento
    WHERE not (presupuesto >=100000 AND presupuesto <=200000);
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    | Proyectos        |           0 |
    | Publicidad       |           0 |
    +------------------+-------------+
    4 rows in set (0,00 sec)
    
    ```

25. Devuelve una lista con el nombre de los departamentos que tienen un
    presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.

    ```sql
    SELECT nombre, presupuesto 
    FROM departamento 
    WHERE presupuesto BETWEEN 100000 AND 200000;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Desarrollo   |      120000 |
    | Sistemas     |      150000 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    3 rows in set (0,00 sec)
    
    ```

26. Devuelve una lista con el nombre de los departamentos que no tienen un
    presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.

    ```sql
    SELECT nombre, presupuesto  
    FROM departamento  
    WHERE NOT (presupuesto BETWEEN 100000 AND 200000);
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    | Proyectos        |           0 |
    | Publicidad       |           0 |
    +------------------+-------------+
    4 rows in set (0,00 sec)
    
    ```

27. Devuelve una lista con el nombre de los departamentos, gastos y
    presupuesto, de aquellos departamentos donde los gastos sean mayores
    que el presupuesto del que disponen.

    ```sql
    SELECT nombre,gasto,presupuesto FROM departamento
    WHERE gasto > presupuesto;
    +------------+--------+-------------+
    | nombre     | gasto  | presupuesto |
    +------------+--------+-------------+
    | I+D        | 380000 |      375000 |
    | Publicidad |   1000 |           0 |
    +------------+--------+-------------+
    2 rows in set (0,00 sec)
    
    ```

28. Devuelve una lista con el nombre de los departamentos, gastos y
    presupuesto, de aquellos departamentos donde los gastos sean menores
    que el presupuesto del que disponen.

    ```sql
    SELECT nombre,gasto,presupuesto 
    FROM departamento 
    WHERE gasto < presupuesto;
    +------------------+-------+-------------+
    | nombre           | gasto | presupuesto |
    +------------------+-------+-------------+
    | Desarrollo       |  6000 |      120000 |
    | Sistemas         | 21000 |      150000 |
    | Recursos Humanos | 25000 |      280000 |
    | Contabilidad     |  3000 |      110000 |
    +------------------+-------+-------------+
    4 rows in set (0,00 sec)
    
    ```

    29. Devuelve una lista con el nombre de los departamentos, gastos y
        presupuesto, de aquellos departamentos donde los gastos sean iguales al
        presupuesto del que disponen.

        ```sql
        SELECT nombre,gasto,presupuesto 
        FROM departamento W
        HERE gasto = presupuesto;
        +-----------+-------+-------------+
        | nombre    | gasto | presupuesto |
        +-----------+-------+-------------+
        | Proyectos |     0 |           0 |
        +-----------+-------+-------------+
        1 row in set (0,00 sec)
        
        ```

    30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL.

        ```sql
        SELECT codigo, nif, nombre, apellido1, apellido2, codigo 
        FROM empleado 
        WHERE apellido2 IS NULL;
        +--------+-----------+---------+-----------+-----------+--------+
        | codigo | nif       | nombre  | apellido1 | apellido2 | codigo |
        +--------+-----------+---------+-----------+-----------+--------+
        |      4 | 77705545E | Adrián  | Suárez    | NULL      |      4 |
        |      7 | 80576669X | Pilar   | Ruiz      | NULL      |      7 |
        +--------+-----------+---------+-----------+-----------+--------+
        2 rows in set (0,00 sec)
        
        ```

    31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL.

        ```sql
        SELECT codigo, nif, nombre, apellido1, apellido2, codigo 
        FROM empleado 
        WHERE apellido2 IS NOT NULL;
        +--------+-----------+--------------+-----------+-----------+--------+
        | codigo | nif       | nombre       | apellido1 | apellido2 | codigo |
        +--------+-----------+--------------+-----------+-----------+--------+
        |      1 | 32481596F | Aarón        | Rivero    | Gómez     |      1 |
        |      2 | Y5575632D | Adela        | Salas     | Díaz      |      2 |
        |      3 | R6970642B | Adolfo       | Rubio     | Flores    |      3 |
        |      5 | 17087203C | Marcos       | Loyola    | Méndez    |      5 |
        |      6 | 38382980M | María        | Santana   | Moreno    |      6 |
        |      8 | 71651431Z | Pepe         | Ruiz      | Santana   |      8 |
        |      9 | 56399183D | Juan         | Gómez     | López     |      9 |
        |     10 | 46384486H | Diego        | Flores    | Salas     |     10 |
        |     11 | 67389283A | Marta        | Herrera   | Gil       |     11 |
        |     12 | 41234836R | Irene        | Salas     | Flores    |     12 |
        |     13 | 82635162B | Juan Antonio | Sáez      | Guerrero  |     13 |
        +--------+-----------+--------------+-----------+-----------+--------+
        11 rows in set (0,00 sec)
        ```

        

    32. Lista todos los datos de los empleados cuyo segundo apellido sea López.

        ```sql
        SELECT codigo, nif, nombre, apellido1, apellido2, codigo  
        FROM empleado  
        WHERE apellido2 = "López";
        +--------+-----------+--------+-----------+-----------+--------+
        | codigo | nif       | nombre | apellido1 | apellido2 | codigo |
        +--------+-----------+--------+-----------+-----------+--------+
        |      9 | 56399183D | Juan   | Gómez     | López     |      9 |
        +--------+-----------+--------+-----------+-----------+--------+
        1 row in set (0,00 sec)
        
        ```

    33. Lista todos los datos de los empleados cuyo segundo apellido
        sea Díaz o Moreno. Sin utilizar el operador IN.

        ```sql
        SELECT codigo, nif, nombre, apellido1, apellido2, codigo
        FROM empleado
        WHERE apellido2 = 'Díaz' OR apellido2 = 'Moreno';
        +--------+-----------+--------+-----------+-----------+--------+
        | codigo | nif       | nombre | apellido1 | apellido2 | codigo |
        +--------+-----------+--------+-----------+-----------+--------+
        |      2 | Y5575632D | Adela  | Salas     | Díaz      |      2 |
        |      6 | 38382980M | María  | Santana   | Moreno    |      6 |
        +--------+-----------+--------+-----------+-----------+--------+
        2 rows in set (0,00 sec)
        
        ```

    34. Lista todos los datos de los empleados cuyo segundo apellido
        sea Díaz o Moreno. Utilizando el operador IN.

        ```sql
        SELECT codigo, nif, nombre, apellido1, apellido2, codigo
        FROM empleado
        WHERE apellido2 IN ('Díaz', 'Moreno');
        +--------+-----------+--------+-----------+-----------+--------+
        | codigo | nif       | nombre | apellido1 | apellido2 | codigo |
        +--------+-----------+--------+-----------+-----------+--------+
        |      2 | Y5575632D | Adela  | Salas     | Díaz      |      2 |
        |      6 | 38382980M | María  | Santana   | Moreno    |      6 |
        +--------+-----------+--------+-----------+-----------+--------+
        2 rows in set (0,00 sec)
        
        ```

    35. Lista los nombres, apellidos y nif de los empleados que trabajan en el
        departamento 3.

        ```sql
        SELECT nombre,apellido1,apellido2,nif
        FROM empleado
        WHERE codigo_departamento = 3;
        +--------+-----------+-----------+-----------+
        | nombre | apellido1 | apellido2 | nif       |
        +--------+-----------+-----------+-----------+
        | Adolfo | Rubio     | Flores    | R6970642B |
        | Pepe   | Ruiz      | Santana   | 71651431Z |
        +--------+-----------+-----------+-----------+
        2 rows in set (0,00 sec)
        
        ```

    36. Lista los nombres, apellidos y nif de los empleados que trabajan en los
        departamentos 2, 4 o 5.

        ```sql
        SELECT nombre,apellido1,apellido2,nif
        FROM empleado
        WHERE codigo_departamento IN (2,4,5);
        +---------+-----------+-----------+-----------+
        | nombre  | apellido1 | apellido2 | nif       |
        +---------+-----------+-----------+-----------+
        | Adela   | Salas     | Díaz      | Y5575632D |
        | Adrián  | Suárez    | NULL      | 77705545E |
        | Marcos  | Loyola    | Méndez    | 17087203C |
        | Pilar   | Ruiz      | NULL      | 80576669X |
        | Juan    | Gómez     | López     | 56399183D |
        | Diego   | Flores    | Salas     | 46384486H |
        +---------+-----------+-----------+-----------+
        6 rows in set (0,00 sec)
        
        ```

        # Consultas multitabla (Composición interna)

        ### Resuelva todas las consultas utilizando la sintaxis de SQL1 y SQL2.

        1. Devuelve un listado con los empleados y los datos de los departamentos
            donde trabaja cada uno.

          ```sql
          SELECT e.nombre AS nombre_empleado, e.apellido1, e.apellido2, e.nif, 
          d.nombre AS nombre_departamento, d.presupuesto
          FROM empleado e
          JOIN departamento d ON e.codigo_departamento = d.codigo;
          +-----------------+-----------+-----------+-----------+---------------------+-------------+
          | nombre_empleado | apellido1 | apellido2 | nif       | nombre_departamento | presupuesto |
          +-----------------+-----------+-----------+-----------+---------------------+-------------+
          | Aarón           | Rivero    | Gómez     | 32481596F | Desarrollo          |      120000 |
          | Adela           | Salas     | Díaz      | Y5575632D | Sistemas            |      150000 |
          | Adolfo          | Rubio     | Flores    | R6970642B | Recursos Humanos    |      280000 |
          | Adrián          | Suárez    | NULL      | 77705545E | Contabilidad        |      110000 |
          | Marcos          | Loyola    | Méndez    | 17087203C | I+D                 |      375000 |
          | María           | Santana   | Moreno    | 38382980M | Desarrollo          |      120000 |
          | Pilar           | Ruiz      | NULL      | 80576669X | Sistemas            |      150000 |
          | Pepe            | Ruiz      | Santana   | 71651431Z | Recursos Humanos    |      280000 |
          | Juan            | Gómez     | López     | 56399183D | Sistemas            |      150000 |
          | Diego           | Flores    | Salas     | 46384486H | I+D                 |      375000 |
          | Marta           | Herrera   | Gil       | 67389283A | Desarrollo          |      120000 |
          +-----------------+-----------+-----------+-----------+---------------------+-------------+
          11 rows in set (0,00 sec)
          ```

          

        2. Devuelve un listado con los empleados y los datos de los departamentos
            donde trabaja cada uno. Ordena el resultado, en primer lugar por el nombre
            del departamento (en orden alfabético) y en segundo lugar por los apellidos
            y el nombre de los empleados.

          

        ```sql
        SELECT e.nombre AS nombre_empleado, e.apellido1, e.apellido2, d.nombre AS nombre_departamento
        FROM empleado e
        JOIN departamento d ON e.codigo_departamento = d.codigo
        ORDER BY d.nombre, e.apellido1, e.apellido2, e.nombre;
        +-----------------+-----------+-----------+---------------------+
        | nombre_empleado | apellido1 | apellido2 | nombre_departamento |
        +-----------------+-----------+-----------+---------------------+
        | Adrián          | Suárez    | NULL      | Contabilidad        |
        | Marta           | Herrera   | Gil       | Desarrollo          |
        | Aarón           | Rivero    | Gómez     | Desarrollo          |
        | María           | Santana   | Moreno    | Desarrollo          |
        | Diego           | Flores    | Salas     | I+D                 |
        | Marcos          | Loyola    | Méndez    | I+D                 |
        | Adolfo          | Rubio     | Flores    | Recursos Humanos    |
        | Pepe            | Ruiz      | Santana   | Recursos Humanos    |
        | Juan            | Gómez     | López     | Sistemas            |
        | Pilar           | Ruiz      | NULL      | Sistemas            |
        | Adela           | Salas     | Díaz      | Sistemas            |
        +-----------------+-----------+-----------+---------------------+
        11 rows in set (0,00 sec)
        
        ```
        
        3. Devuelve un listado con el identificador y el nombre del departamento,
             solamente de aquellos departamentos que tienen empleados.
        
             ```sql
             SELECT d.codigo, d.nombre
             FROM departamento d
             INNER JOIN empleado e ON d.codigo = e.codigo_departamento;
             +--------+------------------+
             | codigo | nombre           |
             +--------+------------------+
             |      1 | Desarrollo       |
             |      2 | Sistemas         |
             |      3 | Recursos Humanos |
             |      4 | Contabilidad     |
             |      5 | I+D              |
             |      1 | Desarrollo       |
             |      2 | Sistemas         |
             |      3 | Recursos Humanos |
             |      2 | Sistemas         |
             |      5 | I+D              |
             |      1 | Desarrollo       |
             +--------+------------------+
             11 rows in set (0,00 sec)
             
             ```
        
        4. Devuelve un listado con el identificador, el nombre del departamento y el
             valor del presupuesto actual del que dispone, solamente de aquellos
               departamentos que tienen empleados. El valor del presupuesto actual lo
               puede calcular restando al valor del presupuesto inicial
               (columna presupuesto) el valor de los gastos que ha generado
               (columna gastos).
        
             ```sql
              SELECT d.codigo, d.nombre, (d.presupuesto - d.gasto) AS presupuesto_actual
             FROM departamento d
             INNER JOIN empleado e ON d.codigo = e.codigo_departamento;
             +--------+------------------+--------------------+
             | codigo | nombre           | presupuesto_actual |
             +--------+------------------+--------------------+
             |      1 | Desarrollo       |             114000 |
             |      2 | Sistemas         |             129000 |
             |      3 | Recursos Humanos |             255000 |
             |      4 | Contabilidad     |             107000 |
             |      5 | I+D              |              -5000 |
             |      1 | Desarrollo       |             114000 |
             |      2 | Sistemas         |             129000 |
             |      3 | Recursos Humanos |             255000 |
             |      2 | Sistemas         |             129000 |
             |      5 | I+D              |              -5000 |
             |      1 | Desarrollo       |             114000 |
             +--------+------------------+--------------------+
             11 rows in set (0,00 sec)
             
             ```
        
             
        
        5. Devuelve el nombre del departamento donde trabaja el empleado que tiene
             el nif 38382980M.
        
        ```sql
        SELECT departamento.nombre
        FROM empleado
        JOIN departamento ON empleado.codigo_departamento = departamento.codigo
        WHERE empleado.nif = '38382980M';
        +------------+
        | nombre     |
        +------------+
        | Desarrollo |
        +------------+
        1 row in set (0,00 sec)
        ```
        
        

6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz
  Santana.

  ```sql
   SELECT departamento.nombre
  FROM empleado
  JOIN departamento ON empleado.codigo_departamento = departamento.codigo
  WHERE empleado.nombre = 'Pepe' AND empleado.apellido1 = 'Ruiz' AND empleado.apellido2 = 'Santana';
  +------------------+
  | nombre           |
  +------------------+
  | Recursos Humanos |
  +------------------+
  1 row in set (0,00 sec)
  
  ```

  

7. Devuelve un listado con los datos de los empleados que trabajan en el
  departamento de I+D. Ordena el resultado alfabéticamente.

  ```sql
  SELECT empleado.codigo, empleado.nif, empleado.nombre, empleado.apellido1, empleado.apellido2, empleado.codigo_departamento
  FROM empleado
  WHERE empleado.codigo_departamento = (
  SELECT codigo
  FROM departamento
  WHERE nombre = 'I+D')
  ORDER BY empleado.nombre, empleado.apellido1, empleado.apellido2;
  +--------+-----------+--------+-----------+-----------+---------------------+
  | codigo | nif       | nombre | apellido1 | apellido2 | codigo_departamento |
  +--------+-----------+--------+-----------+-----------+---------------------+
  |     10 | 46384486H | Diego  | Flores    | Salas     |                   5 |
  |      5 | 17087203C | Marcos | Loyola    | Méndez    |                   5 |
  +--------+-----------+--------+-----------+-----------+---------------------+
  2 rows in set (0,00 sec)
  
  ```

  

8. Devuelve un listado con los datos de los empleados que trabajan en el
  departamento de Sistemas, Contabilidad o I+D. Ordena el resultado
  alfabéticamente.

  ```sql
  SELECT empleado.codigo, empleado.nif, empleado.nombre, empleado.apellido1, empleado.apellido2, empleado.codigo_departamento
  FROM empleado
  WHERE empleado.codigo_departamento IN (
  SELECT codigo
  FROM departamento
  WHERE nombre IN ('Sistemas', 'Contabilidad', 'I+D')
  )
  ORDER BY empleado.nombre, empleado.apellido1, empleado.apellido2;
  +--------+-----------+---------+-----------+-----------+---------------------+
  | codigo | nif       | nombre  | apellido1 | apellido2 | codigo_departamento |
  +--------+-----------+---------+-----------+-----------+---------------------+
  |      2 | Y5575632D | Adela   | Salas     | Díaz      |                   2 |
  |      4 | 77705545E | Adrián  | Suárez    | NULL      |                   4 |
  |     10 | 46384486H | Diego   | Flores    | Salas     |                   5 |
  |      9 | 56399183D | Juan    | Gómez     | López     |                   2 |
  |      5 | 17087203C | Marcos  | Loyola    | Méndez    |                   5 |
  |      7 | 80576669X | Pilar   | Ruiz      | NULL      |                   2 |
  +--------+-----------+---------+-----------+-----------+---------------------+
  6 rows in set (0,00 sec)
  
  ```

  

9. Devuelve una lista con el nombre de los empleados que tienen los
  departamentos que no tienen un presupuesto entre 100000 y 200000 euros.

  ```sql
  SELECT empleado.nombre
  FROM empleado
  WHERE empleado.codigo_departamento NOT IN (
  SELECT codigo
  FROM departamento
  WHERE presupuesto BETWEEN 100000 AND 200000
  );
  +--------+
  | nombre |
  +--------+
  | Adolfo |
  | Marcos |
  | Pepe   |
  | Diego  |
  +--------+
  4 rows in set (0,00 sec)
  
  ```

  

10. Devuelve un listado con el nombre de los departamentos donde existe
    algún empleado cuyo segundo apellido sea NULL. Tenga en cuenta que no
    debe mostrar nombres de departamentos que estén repetidos.

```sql
SELECT DISTINCT departamento.nombre
FROM empleado
JOIN departamento ON empleado.codigo_departamento = departamento.codigo
WHERE empleado.apellido2 IS NULL;
+--------------+
| nombre       |
+--------------+
| Contabilidad |
| Sistemas     |
+--------------+
2 rows in set (0,00 sec)


```

# Consultas multitabla (Composición externa)

### Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.

1. Devuelve un listado con todos los empleados junto con los datos de los
departamentos donde trabajan. Este listado también debe incluir los
empleados que no tienen ningún departamento asociado.
2. Devuelve un listado donde sólo aparezcan aquellos empleados que no
tienen ningún departamento asociado.
3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no
tienen ningún empleado asociado.
4. Devuelve un listado con todos los empleados junto con los datos de los
departamentos donde trabajan. El listado debe incluir los empleados que no
tienen ningún departamento asociado y los departamentos que no tienen
ningún empleado asociado. Ordene el listado alfabéticamente por el
nombre del departamento.
5. Devuelve un listado con los empleados que no tienen ningún departamento
asociado y los departamentos que no tienen ningún empleado asociado.
Ordene el listado alfabéticamente por el nombre del departamento.