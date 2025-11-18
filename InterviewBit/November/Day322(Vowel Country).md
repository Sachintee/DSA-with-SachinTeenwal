SELECT COUNT(Country) AS `COUNT(Country)`
FROM PLACES
WHERE LOWER(RIGHT(Country, 1)) IN ('a', 'e', 'i', 'o', 'u');
