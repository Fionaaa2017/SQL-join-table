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

"Now, create another query that will result in one row per each customer, with their name, email, and total amount of money they've spent on orders. Sort the rows according to the total money spent, from the most spent to the least spent.
(Tip: You should always GROUP BY on the column that is most likely to be unique in a row.)"

Select customers.name,customers.email,orders.item,orders.price from customers left outer join orders on customers.id=orders.customer_id;

"Now, create another query that will result in one row per each customer, with their name, email, and total amount of money they've spent on orders. Sort the rows according to the total money spent, from the most spent to the least spent.
(Tip: You should always GROUP BY on the column that is most likely to be unique in a row.)"

Select customers.name,customers.email,sum(orders.price) from customers left outer join orders on customers.id=orders.customer_id group by customers.name order by sum(orders.price) desc;

"We've created a table with all the 'Harry Potter' movies, with a sequel_id column that matches the id of the sequel for each movie. Issue a SELECT that will show the title of each movie next to its sequel's title (or NULL if it doesn't have a sequel)."

select sequel.title,movies.title as sequel_title from movies sequel left outer join movies  on sequel.sequel_id=movies.id;

"Now, use another SELECT with a JOIN to show the names of each pair of friends, based on the data in the friends table"

select a.fullname,b.fullname from friends 
    join persons a 
    on friends.person1_id=a.id
    join persons b 
    on friends.person2_id=b.id; 
