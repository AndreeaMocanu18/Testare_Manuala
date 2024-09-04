<h1>Database Project for *Studenti*</h1>

The scope of this project is to use all the SQL knowledge gained throught the Software Testing course and apply them in practice.

Application under test: <strong>Studenti database</strong>

Tools used: <strong>MySQL Workbench</strong>

Database description: The project consists in creating a database called <strong>"Studenti"</strong>, that consists of five tables with links between them, SQL commands suitable for adding lines with information and displaying data through the application. The five tables will contain information about students, personal data about them, including faculty, grades and subjects. 


<h2><li>Database Schema</li></h2>
<br>
  
You can find below the database schema that was generated through Reverse Engineer and which contains all the tables and the relationships between them.

The tables are connected in the following way:

<ul>
  <li> Tabela "Facultate" is connected with tabela "Informatii_studenti" through a one-to-one relationship which was implemented through Facultate.id as a primary key </li>
  <li> Tabela "materii" is connected with tabela "note" and "studenti" through a one-to-many relationship which was implemented through materii.id as a primary key</li>

  Reverse engineer: 
  ![Untitled](https://github.com/user-attachments/assets/1b0819d7-048f-4e5a-8193-0027aa648753)
  ![Untitled2](https://github.com/user-attachments/assets/1a7e6ec1-b25c-4c46-8a43-c33f75924bb7)


 
<li>Database Queries</li><br>

<ol type="1">
  <h2><li>DDL (Data Definition Language)</li></h2>

  The following instructions were written in the scope of CREATING the structure of the database (CREATE INSTRUCTIONS)

  To create the database, I had used the CREATE SQL command : "create database Studenti;".
  For this database, there had been five tabeles creates : "facultate, informatii_studenti, materii, note,and studenti". Also, the tables were created using the CREATE SQL command :
  <ol>

  <h5><li>create table Facultate</li></h5>
 create table Facultate<br>
(id int primary key not null auto_increment,<br>
nume_facultate varchar(50) not null, <br>
departament_facultate varchar(50) not null,<br>
adresa varchar(50) not null);<br>

  <h5><li>create table Informatii_studenti</li></h5>
create table Informatii_studenti<br>
(id int not null primary key auto_increment,<br>
nume_student varchar(20) not null,<br>
prenume_student varchar(25) not null,<br>
CNP varchar(13) not null,<br>
data_nasterii date not null, <br>
adresa_domiciliu varchar (50) not null,<br>
oras varchar (20),<br>
email varchar(50) not null, <br>
nume_mama varchar(30) not null,<br>
nume_tata varchar(30) not null,<br>
nr_telefon varchar(13) not null); <br>
    
  <h5><li>create table Materii</li></h5>
create table Materii<br>
(id int not null primary key auto_increment,<br>
nume_student varchar(40) not null,<br>
nume_materie varchar(30) not null,<br>
An year,<br>
nume_profesor varchar(30) not null ); <br>

  <h5><li>create table Note</li></h5>
create table Note<br>
(id int not null primary key auto_increment,<br>
nume_student varchar(30) not null,<br>
nume_materie varchar(30) not null, <br>
nota int,<br>
data date not null);<br>
  
<h5><li>create table Studenti</li></h5>
create table Studenti<br>
(id int primary key not null auto_increment,<br>
nume_student varchar(40) not null,<br>
nume_materii varchar(40) not null,<br>
An year,<br>
Grupa int,<br>
Media decimal (6,2),<br>
Bursa varchar (2) ); <br>
</ol>

  
<ol>After the database and the tables have been created, a few ALTER instructions were written in order to update the structure of the database, as described below:</ol>

<em>alter table Studenti
modify column Bursa varchar (10);</em> - to modify the column Bursa

<em>alter table informatii_studenti 
drop column CNP;</em> - to delete the column CNP from the table informatii_studenti
 
  
<h2><li>DML (Data Manipulation Language)</li></h2>
  In order to be able to use the database I populated the tables with various data necessary in order to perform queries and manipulate the data. 
  In the testing process, this necessary data is identified in the Test Design phase and created in the Test Implementation phase. 

  Below you can find all the insert instructions that were created in the scope of this project:

1. <strong>insert into facultate</strong> (id, nume_facultate, departament_facultate, adresa)
<ol>values<br>
(1,"Universitatea din București", "Facultatea de Geografie", "Bd. Nicolae Bălcescu nr.1, Bucureşti"), <br>
(2,"Universitatea din București", "Facultatea de Biologie", "Splaiul Independenței nr. 91–95, București"),<br>
(3,"Universitatea din București", "Facultatea de Litere", "Str. Edgar Quinet nr. 5-7, București"),<br>
(4,"Universitatea din București", "Facultatea de Matematică și Informatică", "Str. Academiei nr. 14, București"),<br>
(5,"Universitatea din București", "Facultatea de Limbi și Literaturi Străine", "Str. Edgar Quinet nr. 5–7, Bucureşti");  <br>
In the table "Facultate" there had been added the above information in the form of rows.</ol>

2. <strong>insert into Note</strong> (id,nume_student, nume_materie, nota, data) 
<ol>values<br>
(1,"Balacu Maria", "Botanică și Microbiologie", 7, "2003-06-20"),<br>
(2,"Grigoras Tudor", "Studii Literare", 9, "2003-06-18"),<br>
(3,"Anton Mirela", "Matematică", 10, "2003-06-20"),<br>
(4,"Visan Oana", "Engleză" , 9, "2003-06-18"),<br>
(5,"Popescu Cristian", "Geografie Umană și Economică", 8, "2003-06-20");<br>
In the table "Note" there had been added the above information in the form of rows.</ol>

3. <strong>insert into Studenti</strong> (id, nume_student, nume_materii, An, Grupa, Media,Bursa)
<ol>values<br>
(1, "Balacu Maria", "Botanică și Microbiologie", "2003",  4, 8.30, "nu"),<br>
(2, "Grigoras Tudor", "Studii Literare", "2003", 1, 10, "da"),<br>
(3, "Anton Mirela", "Matematică ", "2003", 3, 9.20, "da"),<br>
(4, "Visan Oana", "Engleză","2003",  2, 9.77, "da"),<br>
(5, "Popescu Cristian", "Geografie Umană și Economică", "2003", 5, 7.30, "nu");<br>
In the table "Studenti" there had been added the above information in the form of rows.</ol>

4. <strong>insert into Materii</strong> (id, nume_student, nume_materie, An, nume_profesor)
<ol>values<br>
(1,"Balacu Maria", "Botanică și Microbiologie", 2003, "Lia Mara Dițu"), <br>
(2,"Grigoras Tudor", "Studii Literare", 2003, "Mircea Vasilescu"),<br>
(3,"Anton Mirela", "Matematică", 2003, "Ionel Popescu"),<br>
(4,"Visan Oana", "Engleză", 2003, "Dragoș Ivana");  <br>
In the table "Materii" there had been added the above information in the form of rows.</ol>

5. <strong>insert into Informatii_studenti</strong> (id, nume_student, prenume_student, CNP, data_nasterii, adresa_domiciliu, oras, email, nume_mama, nume_tata, nr_telefon) 
<ol>values<br>
(1, "Balacu", "Maria", 6020712088859, "2002-07-12" , "Strada Lalelor 18, bloc 2, etaj 5, apt 30", "Brasov", "maria.balacu@gmail.com", "Balacu Mirela", "Balacu Ion", 0747977892),<br>
(2, "Grigoras", "Tudor", 5011228463591, "2001-12-28", "Strada Margaretei 20, bloc A, etaj 1, apt 4", "Bucuresti", "tudor.grigoras@yahoo.com", "Grigoras Ioana", "Grigoras Marian", 0743200192), <br>
(3, "Anton", "Mirela", 6020818170974, "2002-08-18", "Strada Blaj 18, bloc B8, etaj 5, apt 38", "Calarasi", "anton.mirela@gmail.com", " Anton Oana", "Anton Mirel", 0741203211), <br>
(4, "Visan", "Oana", 2970314469899, "1997-03-14", "Strada Brandusei 31", "Bucuresti", "oana.v@gmail.com", "Visan Mirela", "Visan Andrei", 0770324565),<br>
(5, "Popescu", "Cristian", 6030221512692, "2003-01-21", "Strada Fantanii 20", "Calarasi", "c.popescu@yahoo.com", "Popescu Maria", "Popescu Dragos", 0770654719);<br>
In the table "Informatii_studenti" there had been added the above information in the form of rows.
Each value insert had been of the same datatype as the respective column and confirmed of the constraints of the column (if any). The values passed using the insert statement into the tables.</ol>


  After the insert, in order to prepare the data to be better suited for the testing process, I updated some data in the following way:

<ol>
1. To replace the name from the table "informatii_studenti of one of the parent based on the condition: 
  <strong>update informatii_studenti set nume_mama = "Balacu Antonia" where id=1;</strong>
  
2. To replace the addres from the table "informatii_studenti" based on the condition: 
<strong>update informatii_studenti set adresa_domiciliu = "Strada Rezervelor 48, bloc 5, etaj 5, ap.501" where nume_student = "Visan";</strong>

3. To replace the name of one university:
<strong>update facultate set nume_facultate = "ASE" where id=3;</strong>

4. To modify the year from the "materii" table:
<strong>update materii set an=2004 where id=3;</strong>

5. To modify the place from the "informatii_studenti" table where the email ends with the specified value:
<strong>update informatii_studenti set oras="Brasov" where email like "%visan";</strong>

6. To modify the email from the "informatii_studenti" table where the student name starts with the specified value :
<strong>update informatii_studenti set email = "tdr.grig@gmail.com" where prenume_student like "tudor%";</strong>

7. To update the name of the teacher from the table "materii" : 
<strong>update materii set nume_profesor="Marcel Pavel" where an between 2006 and 2013;</strong>
</ol>

 <h2><li>DQL (Data Query Language)</li></h2>

<ol>After the testing process, I deleted the data that was no longer relevant in order to preserve the database clean: 

<em>alter table informatii_studenti 
drop column CNP;</em> - to delete the column CNP from the table informatii_studenti</ol>

In order to simulate various scenarios that might happen in real life I created the following queries that would cover multiple potential real-life situations:


1. <strong>select nume_student, nume_materii, grupa from studenti where media >9.60; </strong>

2. <strong>select nume_student, nume_materii, grupa, media from studenti where media < 9.60; </strong>

3. <strong>select departament_facultate, adresa from facultate where adresa like "%5%";</strong> - to select the departament_facultate, adresa from "facultate" where the address contains the number "5"

4. <strong>select departament_facultate, adresa from facultate where adresa like "str.%";</strong> - to extract the departament_facultate, adresa from "facultate" where the address begins with "str."

5. <strong>select departament_facultate, adresa from facultate where nume_facultate like "%Bucuresti";</strong> - to extract the departament_facultate, adresa from "facultate" where the nume_facultate ends with "Bucuresti"

6. <strong>select nume_student, prenume_student, adresa_domiciliu from informatii_studenti where oras="Bucuresti" or data_nasterii="2003-01-21";</strong> - to extract the data from "informatii_studenti" based on the conditions: the city has to be Bucuresti or date of birth is 2003-01-21. 

7. <strong>select nume_student, prenume_student, adresa_domiciliu from informatii_studenti where oras="Bucuresti" and data_nasterii="1997-03-14";</strong>- to extract the data from "informatii_studenti" where the city is Bucuresti and date of birth is 1997-03-14

8. <strong>select nume_student, nume_materie, nota, data from note join facultate; </strong>

9. <strong>select an, grupa, media, bursa from studenti 
join note on studenti.id=note.id; </strong>

10. <strong>select prenume_student, oras, nume_mama, nume_tata
from informatii_studenti 
left join materii on informatii_studenti.id=materii.id; </strong>

11. <strong>select nume_facultate, departament_facultate from facultate
right join materii
on facultate.id=materii.id;</strong>

12. <strong>select max(nota) from note;</strong> - to select the highest grade from "note" 

13. <strong>select max(media) from studenti;</strong> - to select the highest media from "studenti" 

14. <strong>select min(nota) from note;</strong> - to extract the lowest grade from "note" 

15. <strong>select min(media) from studenti;</strong> -to extract the lowest media from "studenti" 

16. <strong>select adresa_domiciliu, nume_mama, nume_tata
from informatii_studenti
inner join facultate on facultate.id=informatii_studenti.id
where oras="Bucuresti";</strong>

17. <strong>select nume_facultate, departament_facultate, adresa
from facultate
right join note on note.id=facultate.id
where data="2003-06-18";</strong>

18. <strong>select nume_facultate, departament_facultate, adresa
from facultate
inner join note on note.id=facultate.id
inner join materii on materii.id=facultate.id
where data="2003-06-18"; </strong>

19. <strong>SELECT nume_materie, nume_profesor
FROM materii
INNER JOIN studenti
ON materii.id = studenti.id 
WHERE media > 9.00;</strong>

20. <strong>select an, grupa, media, bursa from studenti 
cross join note on studenti.id=note.id;</strong>

21. <strong>select nume_student, nume_materie from materii order by an;</strong>

22. <strong>select nume_student, prenume_student, adresa_domiciliu from informatii_studenti order by oras;</strong>
    
23. <strong>select nume_student, nume_materii, bursa from studenti order by media asc;</strong>  to select the nume_student, nume_materii, bursa from "studenti" and sort in an asscending order the media

24. <strong>select nume_student, nume_materii, bursa from studenti order by media desc limit 3;</strong> - to select the nume_student, nume_materii, bursa from "studenti" and sort in an descending order the media by restricting the number of results. 
<br>

</ol>

<h3><li><strong>Conclusion</strong></li></h3>

For this project, the SQL language was used which is a specialized language used to manage and manipulate relational databases on different operating systems. The MySQL Workbench application was used to create the Students database, and to organize the data collection.​ SQL commands are instructions used in this project to communicate with the database and perform specific tasks.
Working on this project had been motivating, since this was my first interaction with SQL and is was a great experince.

</ol>
