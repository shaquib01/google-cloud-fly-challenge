# Solutions:-
## Task 1

```
SELECT name
FROM `drl.events`
WHERE city = 'Phoenix'
```

## Task 2
```
SELECT p.name as pilot , ep.id as event_pilot_id
FROM `drl.event_pilots` ep
JOIN `drl.pilots` p
ON ep.id = p.id
```

## Task 3
```
SELECT p.name, e.name 
FROM `drl.event_pilots` ep
JOIN `drl.pilots` p
ON ep.id = p.id
JOIN `drl.events` e
ON ep.id = e.id
WHERE e.name = 'Detroit World Championship'
```

## Task 4
```
SELECT time
 (timestamp_seconds
   (CAST
     (AVG
       (UNIX_SECONDS
         (PARSE_TIMESTAMP('%H:%M.%S', minimum_time))
       )
   AS INT64)
   )
 ) as avg
FROM drl.round_standings
WHERE rank = 1
```






