<h1>Database Project for **Studenti**</h1>

The scope of this project is to use all the SQL knowledge gained throught the Software Testing course and apply them in practice.

Application under test: <strong>Studenti database</strong>

Tools used: MySQL Workbench

Database description: The project consists in creating a database called "Studenti", that consists of five tables with links between them, SQL commands suitable for adding lines with information and displaying data through the application. The five tables will contain information about students, personal data about them, including faculty, grades and subjects. 

<ol>
<li>Database Schema </li>
<br>
You can find below the database schema that was generated through Reverse Engineer and which contains all the tables and the relationships between them.

The tables are connected in the following way:

<ul>
  <li> Tabela "Facultate" is connected with tabela "Informatii_studenti" through a one-to-one relationship which was implemented through Facultate.id as a primary key </li>
  <li> Tabela "materii" is connected with tabela "note" and "studenti" through a one-to-many relationship which was implemented through materii.id as a primary key</li>
 
<li>Database Queries</li><br>

<ol type="a">
  <li>DDL (Data Definition Language)</li>

  The following instructions were written in the scope of CREATING the structure of the database (CREATE INSTRUCTIONS)

  To create the database, I had used the CREATE SQL command : "create database Studenti;".
  For this database, there had been five tabeles creates : "facultate, informatii_studenti, materii, note, studenti". Also, the tables were created using the CREATE SQL command :
  1. create table Facultate ;
  2. create table Informatii_studenti; 
  3. create table Materii;
  4. create table Note;
  5. create table Studenti;
  For example : create table Materii
(id int not null primary key auto_increment,
nume_student varchar(40) not null,
nume_materie varchar(30) not null,
An year,
nume_profesor varchar(30) not null 
); 


  After the database and the tables have been created, a few ALTER instructions were written in order to update the structure of the database, as described below:

 alter table Studenti
modify column Bursa varchar (10); - to modify the column Bursa

alter table informatii_studenti 
drop column CNP; - to delete the column CNP from the table informatii_studenti
 
  
  <li>DML (Data Manipulation Language)</li>

  In order to be able to use the database I populated the tables with various data necessary in order to perform queries and manipulate the data. 
  In the testing process, this necessary data is identified in the Test Design phase and created in the Test Implementation phase. 

  Below you can find all the insert instructions that were created in the scope of this project:

1. insert into facultate (id, nume_facultate, departament_facultate, adresa)
values 
(1,"Universitatea din București", "Facultatea de Geografie", "Bd. Nicolae Bălcescu nr.1, Bucureşti"), 
(2,"Universitatea din București", "Facultatea de Biologie", "Splaiul Independenței nr. 91–95, București"),
(3,"Universitatea din București", "Facultatea de Litere", "Str. Edgar Quinet nr. 5-7, București"),
(4,"Universitatea din București", "Facultatea de Matematică și Informatică", "Str. Academiei nr. 14, București"),
(5,"Universitatea din București", "Facultatea de Limbi și Literaturi Străine", "Str. Edgar Quinet nr. 5–7, Bucureşti");  
In the table "Facultate" there had been added the above information in the form of rows.

2. insert into Note (id,nume_student, nume_materie, nota, data) 
values
(1,"Balacu Maria", "Botanică și Microbiologie", 7, "2003-06-20"),
(2,"Grigoras Tudor", "Studii Literare", 9, "2003-06-18"),
(3,"Anton Mirela", "Matematică", 10, "2003-06-20"),
(4,"Visan Oana", "Engleză" , 9, "2003-06-18"),
(5,"Popescu Cristian", "Geografie Umană și Economică", 8, "2003-06-20");
In the table "Note" there had been added the above information in the form of rows.

3. insert into Studenti (id, nume_student, nume_materii, An, Grupa, Media,Bursa)
values
(1, "Balacu Maria", "Botanică și Microbiologie", "2003",  4, 8.30, "nu"),
(2, "Grigoras Tudor", "Studii Literare", "2003", 1, 10, "da"),
(3, "Anton Mirela", "Matematică ", "2003", 3, 9.20, "da"),
(4, "Visan Oana", "Engleză","2003",  2, 9.77, "da"),
(5, "Popescu Cristian", "Geografie Umană și Economică", "2003", 5, 7.30, "nu");
In the table "Studenti" there had been added the above information in the form of rows.

4.insert into Materii (id, nume_student, nume_materie, An, nume_profesor)
values
(1,"Balacu Maria", "Botanică și Microbiologie", 2003, "Lia Mara Dițu"), 
(2,"Grigoras Tudor", "Studii Literare", 2003, "Mircea Vasilescu"),
(3,"Anton Mirela", "Matematică", 2003, "Ionel Popescu"),
(4,"Visan Oana", "Engleză", 2003, "Dragoș Ivana");  
In the table "Materii" there had been added the above information in the form of rows.

5.insert into Informatii_studenti (id, nume_student, prenume_student, CNP, data_nasterii, adresa_domiciliu, oras, email,  
nume_mama, nume_tata, nr_telefon) 
values
(1, "Balacu", "Maria", 6020712088859, "2002-07-12" , "Strada Lalelor 18, bloc 2, etaj 5, apt 30", "Brasov", "maria.balacu@gmail.com", "Balacu Mirela", "Balacu Ion", 0747977892),
(2, "Grigoras", "Tudor", 5011228463591, "2001-12-28", "Strada Margaretei 20, bloc A, etaj 1, apt 4", "Bucuresti", "tudor.grigoras@yahoo.com", "Grigoras Ioana", "Grigoras Marian", 0743200192), 
(3, "Anton", "Mirela", 6020818170974, "2002-08-18", "Strada Blaj 18, bloc B8, etaj 5, apt 38", "Calarasi", "anton.mirela@gmail.com", " Anton Oana", "Anton Mirel", 0741203211), 
(4, "Visan", "Oana", 2970314469899, "1997-03-14", "Strada Brandusei 31", "Bucuresti", "oana.v@gmail.com", "Visan Mirela", "Visan Andrei", 0770324565),
(5, "Popescu", "Cristian", 6030221512692, "2003-01-21", "Strada Fantanii 20", "Calarasi", "c.popescu@yahoo.com", "Popescu Maria", "Popescu Dragos", 0770654719);
In the table "Informatii_studenti" there had been added the above information in the form of rows.
Each value insert had been of the same datatype as the respective column and confirmed of the constraints of the column (if any). The values passed using the insert statement into the tables.

  After the insert, in order to prepare the data to be better suited for the testing process, I updated some data in the following way:

1. To replace the name from the table "informatii_studenti of one of the parent based on the condition: update informatii_studenti set nume_mama = "Balacu Antonia" where id=1; 
2. To replace the addres from the table "informatii_studenti" based on the condition: 
update informatii_studenti set adresa_domiciliu = "Strada Rezervelor 48, bloc 5, etaj 5, ap.501" where nume_student = "Visan"; 
3. To replace the name of one university: 
update facultate set nume_facultate = "ASE" where id=3; 
4. To modify the year from the "materii" table:
update materii set an=2004 where id=3; 
5. To modify the place from the "informatii_studenti" table where the email ends with the specified value:
update informatii_studenti set oras="Brasov" where email like "%visan"; 
6. To modify the email from the "informatii_studenti" table where the student name starts with the specified value :
update informatii_studenti set email = "tdr.grig@gmail.com" where prenume_student like "tudor%"; 
7. To update the name of the teacher from the table "materii" : 
 update materii set nume_profesor="Marcel Pavel" where an between 2006 and 2013;

  <li>DQL (Data Query Language)</li>

After the testing process, I deleted the data that was no longer relevant in order to preserve the database clean: 

alter table informatii_studenti 
drop column CNP; - to delete the column CNP from the table informatii_studenti

In order to simulate various scenarios that might happen in real life I created the following queries that would cover multiple potential real-life situations:

1. select nume_student, nume_materii, grupa from studenti where media >9.60; 

2. select nume_student, nume_materii, grupa, media from studenti where media < 9.60; 

3. select departament_facultate, adresa from facultate where adresa like "%5%";

4. select departament_facultate, adresa from facultate where adresa like "str.%";

5. select departament_facultate, adresa from facultate where nume_facultate like "%Bucuresti";

6. select nume_student, prenume_student, adresa_domiciliu from informatii_studenti where oras="Bucuresti" or data_nasterii="2003-01-21";

7. select nume_student, prenume_student, adresa_domiciliu from informatii_studenti where oras="Bucuresti" and data_nasterii="1997-03-14";

8. select nume_student, nume_materie, nota, data from note join facultate; 

9. select an, grupa, media, bursa from studenti 
join note on studenti.id=note.id; 

10. select prenume_student, oras, nume_mama, nume_tata
from informatii_studenti 
left join materii on informatii_studenti.id=materii.id; 

11. select nume_facultate, departament_facultate from facultate
right join materii
on facultate.id=materii.id;

12. select max(nota) from note;

13. select max(media) from studenti;

14. select min(nota) from note;

15. select min(media) from studenti;

16. select adresa_domiciliu, nume_mama, nume_tata
from informatii_studenti
inner join facultate on facultate.id=informatii_studenti.id
where oras="Bucuresti";

17. select nume_facultate, departament_facultate, adresa
from facultate
right join note on note.id=facultate.id
where data="2003-06-18";

18. select nume_facultate, departament_facultate, adresa
from facultate
inner join note on note.id=facultate.id
inner join materii on materii.id=facultate.id
where data="2003-06-18"; 

19. SELECT nume_materie, nume_profesor
FROM materii
INNER JOIN studenti
ON materii.id = studenti.id 
WHERE media > 9.00;

20. select an, grupa, media, bursa from studenti 
cross join note on studenti.id=note.id; 
<br>

</ol>

<li>Conclusions</li>

For this project, the SQL language was used which is a specialized language used to manage and manipulate relational databases on different operating systems. The MySQL Workbench application was used to create the Students database, and to organize the data collection.​ SQL commands are instructions used in this project to communicate with the database and perform specific tasks.
Working on this project had been motivating, since this was my first interaction with SQL and is was a great experince.

</ol>
