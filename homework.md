# SQL Homework

The local cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.
SELECT * FROM movies;
id |                title                | year | show_time
----+-------------------------------------+------+-----------
 1 | Iron Man                            | 2008 | 20:30
 2 | The Incredible Hulk                 | 2008 | 16:50
 3 | Iron Man 2                          | 2010 | 19:40
 4 | Thor                                | 2011 | 14:20
 5 | Captain America: The First Avenger  | 2011 | 17:55
 6 | Avengers Assemble                   | 2012 | 16:50
 7 | Iron Man 3                          | 2013 | 23:10
 8 | Thor: The Dark World                | 2013 | 22:20
 9 | Batman Begins                       | 2005 | 12:50
10 | Captain America: The Winter Soldier | 2014 | 15:30
11 | Guardians of the Galaxy             | 2014 | 22:50
12 | Avengers: Age of Ultron             | 2015 | 23:45
13 | Ant-Man                             | 2015 | 16:20
14 | Captain America: Civil War          | 2016 | 22:25
15 | Doctor Strange                      | 2016 | 12:50
16 | Guardians of the Galaxy 2           | 2017 | 22:10
17 | Spider-Man: Homecoming              | 2017 | 15:40
18 | Thor: Ragnarok                      | 2017 | 19:35
19 | Black Panther                       | 2018 | 16:50
(19 rows)


2.  Return ONLY the name column from the 'people' table
SELECT * FROM people;
id |       name       
----+------------------
  1 | Ewan Bailey
  2 | Stuart Bell
  3 | Ian Bone
  4 | Collin Bull
  5 | Kimberly Clarke
  6 | Eloise Coveny
  7 | James Davidson
  8 | Kyle Johnston
  9 | Heather Malloch
 10 | Simon McBride
 11 | John Smith
 12 | Carme Mias
 13 | John Page
 14 | Delia Paternina
 15 | Robert Templeton
 16 | Neil Watkins
(16 rows)


3.  Oops! Someone at CodeClan spelled Kimberly's name wrong! Change it to reflect the proper spelling ('Kimberly Clarke' should be 'Kimberly Clark').
UPDATE people SET name = 'Kimberly Clark' WHERE name ='Kimberly Clarke';
id |       name       
----+------------------
 1 | Ewan Bailey
 2 | Stuart Bell
 3 | Ian Bone
 4 | Collin Bull
 6 | Eloise Coveny
 7 | James Davidson
 8 | Kyle Johnston
 9 | Heather Malloch
10 | Simon McBride
11 | John Smith
12 | Carme Mias
13 | John Page
14 | Delia Paternina
15 | Robert Templeton
16 | Neil Watkins
 5 | Kimberly Clark
(16 rows)


4.  Return ONLY your name from the 'people' table.
SELECT * FROM people WHERE id =7

id |      name      
----+----------------
  7 | James Davidson
(1 row)

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM
  movies
WHERE title = 'Batman Begins';

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 20:30
  2 | The Incredible Hulk                 | 2008 | 16:50
  3 | Iron Man 2                          | 2010 | 19:40
  4 | Thor                                | 2011 | 14:20
  5 | Captain America: The First Avenger  | 2011 | 17:55
  6 | Avengers Assemble                   | 2012 | 16:50
  7 | Iron Man 3                          | 2013 | 23:10
  8 | Thor: The Dark World                | 2013 | 22:20
 10 | Captain America: The Winter Soldier | 2014 | 15:30
 11 | Guardians of the Galaxy             | 2014 | 22:50
 12 | Avengers: Age of Ultron             | 2015 | 23:45
 13 | Ant-Man                             | 2015 | 16:20
 14 | Captain America: Civil War          | 2016 | 22:25
 15 | Doctor Strange                      | 2016 | 12:50
 16 | Guardians of the Galaxy 2           | 2017 | 22:10
 17 | Spider-Man: Homecoming              | 2017 | 15:40
 18 | Thor: Ragnarok                      | 2017 | 19:35
 19 | Black Panther                       | 2018 | 16:50



6.  Create a new entry in the 'people' table with the name of one of the instructors.

SELECT * FROM people;

id |       name       
----+------------------
  1 | Ewan Bailey
  2 | Stuart Bell
  3 | Ian Bone
  4 | Collin Bull
  6 | Eloise Coveny
  7 | James Davidson
  8 | Kyle Johnston
  9 | Heather Malloch
 10 | Simon McBride
 11 | John Smith
 12 | Carme Mias
 13 | John Page
 14 | Delia Paternina
 15 | Robert Templeton
 16 | Neil Watkins
 17 | John McCollum
  5 | Kimberly Clark
(17 rows)



7.  John Smith has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM
  people
WHERE name = 'John Smith';

id |       name       
----+------------------
  1 | Ewan Bailey
  2 | Stuart Bell
  3 | Ian Bone
  4 | Collin Bull
  6 | Eloise Coveny
  7 | James Davidson
  8 | Kyle Johnston
  9 | Heather Malloch
 10 | Simon McBride
 12 | Carme Mias
 13 | John Page
 14 | Delia Paternina
 15 | Robert Templeton
 16 | Neil Watkins
 17 | John McCollum
  5 | Kimberly Clark
(16 rows)


8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Avengers: Infinity War', 2018, '00:00');

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 20:30
  2 | The Incredible Hulk                 | 2008 | 16:50
  3 | Iron Man 2                          | 2010 | 19:40
  4 | Thor                                | 2011 | 14:20
  5 | Captain America: The First Avenger  | 2011 | 17:55
  6 | Avengers Assemble                   | 2012 | 16:50
  7 | Iron Man 3                          | 2013 | 23:10
  8 | Thor: The Dark World                | 2013 | 22:20
  9 | Batman Begins                       | 2005 | 12:50
 10 | Captain America: The Winter Soldier | 2014 | 15:30
 11 | Guardians of the Galaxy             | 2014 | 22:50
 12 | Avengers: Age of Ultron             | 2015 | 23:45
 13 | Ant-Man                             | 2015 | 16:20
 14 | Captain America: Civil War          | 2016 | 22:25
 15 | Doctor Strange                      | 2016 | 12:50
 16 | Guardians of the Galaxy 2           | 2017 | 22:10
 17 | Spider-Man: Homecoming              | 2017 | 15:40
 18 | Thor: Ragnarok                      | 2017 | 19:35
 19 | Black Panther                       | 2018 | 16:50
 20 | Avengers: Infinity War              | 2018 | 00:00
(20 rows)


9.  The cinema would also like to make the Guardians movies a back to back feature. Find out the show time of "Guardians of the Galaxy" and set the show time of "Guardians of the Galaxy 2" to start two hours later.

marvel=# update movies set show_time ='00:50' where title = 'Guardians of the Galaxy 2';
UPDATE 1
marvel=# select * from movies where title like 'Guardian%';
 id |           title           | year | show_time
----+---------------------------+------+-----------
 11 | Guardians of the Galaxy   | 2014 | 22:50
 16 | Guardians of the Galaxy 2 | 2017 | 00:50
(2 rows)

## Extension

1.  Research how to delete multiple entries from your table in a single command.

DELETE FROM movies WHERE title IN ('Iron Man', 'Doctor Strange', 'Thor');

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  2 | The Incredible Hulk                 | 2008 | 16:50
  3 | Iron Man 2                          | 2010 | 19:40
  5 | Captain America: The First Avenger  | 2011 | 17:55
  6 | Avengers Assemble                   | 2012 | 16:50
  7 | Iron Man 3                          | 2013 | 23:10
  8 | Thor: The Dark World                | 2013 | 22:20
 10 | Captain America: The Winter Soldier | 2014 | 15:30
 11 | Guardians of the Galaxy             | 2014 | 22:50
 12 | Avengers: Age of Ultron             | 2015 | 23:45
 13 | Ant-Man                             | 2015 | 16:20
 14 | Captain America: Civil War          | 2016 | 22:25
 16 | Guardians of the Galaxy 2           | 2017 | 22:10
 17 | Spider-Man: Homecoming              | 2017 | 15:40
 18 | Thor: Ragnarok                      | 2017 | 19:35
 19 | Black Panther                       | 2018 | 16:50
 20 | Avengers: Infinity War              | 2018 | 00:00
(16 rows)
