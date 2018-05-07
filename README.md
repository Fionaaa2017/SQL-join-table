# SQL-join-table
SQL join table
/*We've created a database of people and hobbies, and each row in hobbies is related to a row in persons via the person_id 

column. In this first step, insert one more row in persons and then one more row in hobbies that is related to the newly 

inserted */

INSERT INTO persons (name,age)values("yixing",28);

INSERT INTO hobbies(person_id,name) values(5,"dancing")


/*elect the 2 tables with a join so that you can see each person's name next to their hobby.*/

select persons.name,hobbies.name from hobbies join persons on hobbies.person_id = persons.id;


/*Now, add an additional query that shows only the name and hobbies of 'Bobby McBobbyFace', using JOIN combined with 

WHERE.*/

select persons.name,hobbies.name from hobbies join persons on hobbies.person_id = persons.id where persons.name ="Bobby 

McBobbyFace";
