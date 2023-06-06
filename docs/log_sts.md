
1.接口统计日志

```sql
SELECT 
path, 
count() times, 
sum(duration) total_duration, 
avg(duration) avg_duration, 
max(duration) max_duration 
FROM 
default.log_server 
where 
logType = 'api' 
group by path 
order by avg(duration) desc 
LIMIT 
1000
```


