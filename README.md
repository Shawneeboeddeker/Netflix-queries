# Netflix-queries
queries from two tables in a Netflix database

select count(*) 
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info"
WHERE type='Movie';

select max(date(date_added))
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info";


/*I am using a Netflix database to determin how many titles are listed*/

SELECT title
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info"
ORDER BY title asc;

/*Below I am joining two tables to find out who the director was for a specific movie title*/

SELECT director
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info" titles
LEFT JOIN  "CharlotteChaze/BreakIntoTech"."netflix_people" people
ON titles.show_id=people.show_id
where titles.title='Bright Star'

/*In the query below I am finding out what the oldest movie was added into the database*/

SELECT title, release_year
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info" titles
ORDER BY release_year asc
LIMIT 1;
