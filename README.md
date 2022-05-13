# Timur Kambachekov SQL
Task 1

```
SELECT name FROM Pilots
JOIN Flights ON Pilots.pilot_id = Flights.second_pilot_id
WHERE MONTH(flight_dt) = 8 AND YEAR(flight_dt) = 2022 AND destination = "SVO"
GROUP BY pilot_id
HAVING COUNT(flight_id) = 3
```

Task 2

```
SELECT DISTINCt name FROM Pilots
JOIN Flights ON (Pilots.pilot_id = Flights.first_pilot_id OR 
                 Pilots.pilot_id = Flights.second_pilot_id)
JOIN Planes ON Flights.plane_id = Planes.plane_id
WHERE cargo_flg = 1 AND quantity > 30 AND age > 45
```

Task 3

```
SELECT DISTINCt name FROM Pilots
JOIN Flights ON Pilots.pilot_id = Flights.first_pilot_id
Join Planes ON Flights.plane_id = Planes.plane_id
WHERE cargo_flg = 1 AND YEAr(flight_dt) = 2022
GROUP BY name
ORDER BY COUNT(name) DESC LIMIT 10
```
