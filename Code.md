#Codes 

```sql

SELECT * FROM `netflix userbase fact dataset`;

SELECT * FROM `netflix dimension dataset`;

SELECT `Plan Duration`, AVG(`Monthly Revenue`) AS avg_monthly_revenue
FROM `netflix userbase fact dataset`
GROUP BY `Plan Duration`;

SELECT Country, `netflix dimension dataset`.`Subscription Type`, 
SUM(`netflix userbase fact dataset`.`Monthly Revenue`) 
AS total_revenue
FROM `netflix userbase fact dataset`
JOIN `netflix dimension dataset` 
ON `netflix userbase fact dataset`.`User ID` = `netflix dimension dataset`.`User ID`
GROUP BY Country, `netflix dimension dataset`.`Subscription Type`;

SELECT COUNT(*) AS missing_age_count
FROM `netflix userbase fact dataset`
WHERE Age IS NULL OR Age < 0;

SELECT AVG(`Monthly Revenue`) AS average_monthly_revenue
FROM `netflix userbase fact dataset`;

SELECT MAX(Age) AS max_age
FROM `netflix userbase fact dataset`;

SELECT AVG(`Plan Duration`) AS average_plan_duration
FROM `netflix userbase fact dataset`;

SELECT Country, `Subscription Type`, COUNT(*) AS subscription_count
FROM `netflix dimension dataset`
GROUP BY Country, `Subscription Type`
ORDER BY Country, subscription_count DESC;

SELECT Gender, Device, COUNT(*) AS usage_count
FROM `netflix dimension dataset`
GROUP BY Gender, Device
ORDER BY Gender, usage_count DESC;

SELECT * FROM `netflix userbase fact dataset`
JOIN `netflix dimension dataset` 
ON `netflix userbase fact dataset`.`User ID` = `netflix dimension dataset`.`User ID`;

```
