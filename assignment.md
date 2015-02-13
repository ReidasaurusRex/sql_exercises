###Non-bonus 
1. ###Show all the tables. <br>
	\dt
2. ###Show all the users. <br>
	
3. ###Show all the data in the owners table. <br>
	SELECT * FROM "owners"; <br>
4. ###Show the names of all owners. <br>
	SELECT name FROM "owners";
	
5. ###Show the ages of all of the owners in ascending order. <br>
	SELECT age FROM "owners" ORDER BY age ASC;
	
6. ###Show the name of an owner whose name is Mary. 
SELECT age FROM "owners" WHERE name = 'Mary';
7. ###Show the age of all owners who are older than 30. 
Select age FROM "owners" WHERE age > 30;
8. ###Show the name of all owners whose name starts with an E. 
Select name FROM "owners" WHERE name LIKE 'E%';
9. ###Add an owner named John who is 33 years old to the owners table.
INSERT INTO "owners" (name, age) VALUES ('John', 33);
10. ###Add an owner named Jane who is 43 years old to the owners table. 
INSERT INTO "owners" (name, age) VALUES ('Jane', 43);
11. ###Change Jane's age to 30. 
UPDATE "owners" SET age=30 WHERE name='Jane' AND age=43;
12. ###Change Jane's name to Janet. 
Expecting #11 completed: UPDATE "owners" SET name='Janet' WHERE name='Jane' AND age=30;
13. ###Add a property named Archstone that has 20 units.
INSERT INTO "properties" (name, number, owner_id) VALUES ('Archstone', 20, 2);
14. ###Delete the owner named Janet.
 DELETE FROM "owners" WHERE name='Janet' AND age=30;
15. ###Show all of the properties in alphabetical order that are not named Archstone and do not have an id of 3 or 5. 
SELECT * FROM "properties" WHERE name <> 'Archstone' AND id NOT IN (3,5) ORDER BY name ASC 
16. ###Count the total number of rows in the properties table.
SELECT COUNT(*) FROM "properties";

17. ###Show the highest age of all owners.
SELECT MAX(age) FROM "owners";
18. ###Show the names of the first three owners in your owners table.
SELECT name FROM "owners" LIMIT 3;
19. ###Create a foreign key that references the owner_id in the owners table and forces the constraint ON DELETE NO ACTION. 
ALTER TABLE "properties" ADD FOREIGN KEY (owner_id) REFERENCES "owners" (id) ON DELETE NO ACTION;

20. ###Show all of the information from the owners table and the properties table in one joined table.
  SELECT * FROM "owners" INNER JOIN "properties" ON owners.id = properties.owner_id;
  