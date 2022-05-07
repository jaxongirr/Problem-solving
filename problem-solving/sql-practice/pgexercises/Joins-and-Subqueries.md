How can you produce a list of the start times for bookings by members named 'David Farrell'?

```sql
SELECT bks.starttime
FROM cd.bookings bks
INNER JOIN cd.members mems
        ON mems.memid = bks.memid
WHERE mems.firstname = 'David'
  AND mems.surname = 'Farrell';
```

How can you produce a list of the start times for bookings for tennis courts, for the date '2012-09-21'? Return a list of start time and facility name pairings, ordered by the time

```sql
SELECT bks.starttime AS start, fcs.name AS name
FROM cd.bookings bks
INNER JOIN cd.facilities fcs
        ON bks.facid = fcs.facid
WHERE
      fcs.name IN ('Tennis Court 1','Tennis Court 2') AND
	  bks.starttime >= '2012-09-21' AND
	  bks.starttime < '2012-09-22'
ORDER BY bks.starttime;
```

How can you output a list of all members who have recommended another member? Ensure that there are no duplicates in the list, and that results are ordered by (surname, firstname)

```sql
SELECT DISTINCT recs.firstname AS firstname,
                recs.surname AS surname
FROM cd.members mems
INNER JOIN cd.members recs
        ON recs.memid = mems.recommendedby
ORDER BY surname, firstname;
```

How can you output a list of all members, including the individual who recommended them (if any)? Ensure that results are ordered by (surname, firstname)

```sql
SELECT mems.firstname AS memfname, mems.surname      AS memsname,
       recs.firstname AS recfname, recs.surname AS  recsname
FROM cd.members mems
LEFT OUTER JOIN cd.members recs
        ON mems.recommendedby = recs.memid
ORDER BY memsname, memfname;
```

How can you produce a list of all members who have used a tennis court? Include in your output the name of the court, and the name of the member formatted as a single column. Ensure no duplicate data, and order by the member name followed by the facility name

```sql
SELECT DISTINCT mems.firstname||' '|| mems.surname AS member, fcs.name AS facility
FROM cd.members mems
INNER JOIN cd.bookings bks
         ON mems.memid = bks.memid
INNER JOIN cd.facilities fcs
        ON bks.facid = fcs.facid
WHERE fcs.name IN('Tennis Court 1', 'Tennis Court 2')
ORDER BY  member, facility;
```

How can you produce a list of bookings on the day of 2012-09-14 which will cost the member (or guest) more than $30? Remember that guests have different costs to members (the listed costs are per half-hour 'slot'), and the guest user is always ID 0. Include in your output the name of the facility, the name of the member formatted as a single column, and the cost. Order by descending cost, and do not use any subqueries

```sql
SELECT mem.firstname||' '||mem.surname AS member,
       fcs.name AS facilty,
	   CASE
	       WHEN mem.memid = 0 THEN
		   bks.slots*fcs.guestcost
		ELSE
		   bks.slots*fcs.membercost
		END AS cost
FROM cd.members mem
INNER JOIN cd.bookings bks
        ON mem.memid = bks.memid
INNER JOIN cd.facilities fcs
        ON bks.facid = fcs.facid
WHERE bks.starttime >= '2012-09-14' AND
      bks.starttime < '2012-09-15' AND (
	  (mem.memid=0 AND bks.slots*fcs.guestcost>30) OR
	  (mem.memid!=0 AND bks.slots*fcs.membercost>30))
ORDER BY cost DESC;
```

How can you output a list of all members, including the individual who recommended them (if any), without using any joins? Ensure that there are no duplicates in the list, and that each firstname + surname pairing is formatted as a column and ordered

```sql
SELECT DISTINCT mem.firstname||' '||mem.surname AS member,
            (SELECT rec.firstname||' '||rec.surname AS recommender
			 FROM cd.members rec
			 WHERE rec.memid = mem.recommendedby)
FROM cd.members mem
ORDER BY member;
```

Produce a list of costly bookings, using a subquery

```sql
SELECT member, facility, cost FROM (
	SELECT
		mems.firstname || ' ' || mems.surname AS member,
		facs.name AS facility,
		CASE
			WHEN mems.memid = 0 THEN
				bks.slots*facs.guestcost
			ELSE
				bks.slots*facs.membercost
		END AS cost
		FROM
			cd.members mems
			INNER JOIN cd.bookings bks
				ON mems.memid = bks.memid
			INNER JOIN cd.facilities facs
				ON bks.facid = facs.facid
		WHERE
			bks.starttime >= '2012-09-14' AND
			bks.starttime < '2012-09-15'
	) AS bookings
	WHERE cost > 30
ORDER BY cost DESC;
```
