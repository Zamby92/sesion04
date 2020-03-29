# sesion04

##Paso 1 conectarse a anaconda powershall

## Paso 2; colocamos este comando y la contraseña que previamente no dio Sergio por slack
>> mycli -u root -h ec2-54-213-51-169.us-west-2.compute.amazonaws.com --local-infile TRUE

##Paso 3; vemos cuales son los dataset, para meter la info
>>show dataset;

##Paso 4; usamos el dataset Zamby
>>use Zamby;

##Subimos el archivo que tenemos del proyecto
>>load DATA LOCAL INFILE "c:/Users/alejandro.zambrano/desktop/Introduccion-a-Base-de-Datos/Sesion-03/Postwork-03/Municipal-Delitos-2015-2020_ene2020/Criminalidad-2015-2020.csv" into table `Criminalidad` FIELDS terminated by ",";
 
##Previamente ya habiamos cargado la tabla, de la siguiente forma
>>create table Criminalidad ( Ano INT, Clave_Ent INT, Cve_Municipio INT, Municipio VARCHAR (50), Bien_juridico_afectado VARCHAR (100), Tipo_de_delito VARCHAR (100), Modalidad VARCHAR (100), Enero INT, Febrero INT, Marzo INT, Abril INT, Mayo INT, Junio INT, Julio INT, Agosto INT, Septiembre INT, Octubre INT, Noviembre INT, Diciembre INT);

##checamos las tablas
>>Show tables;

##Nos metemos a la info de criminalidad
>>select * from Criminalidad;

##El archivo es muy pesado y se tarda casi 8 min en cargar la información
##Seleccionaremos solo el año 2019
>> select * from Criminalidad where "Ano" = 2019;

##Queremos obtener los tipos de delitos para el 2019
>> select distinct(Tipos_de_delito) where "Ano"=2019;

##Ahora queremos saber cuantos tipo de delitos son para cada año 2015, 2016, 2017, 2018, 2019
>> select count (distinct Tipos_de_delitos) where "Ano"=2015;
80
>> select count (distinct Tipos_de_delitos) where "Ano"=2016;
83
>> select count (distinct Tipos_de_delitos) where "Ano"=2017;
83
>> select count (distinct Tipos_de_delitos) where "Ano"=2018;
84
>> select count (distinct Tipos_de_delitos) where "Ano"=2019;
86



 
 
