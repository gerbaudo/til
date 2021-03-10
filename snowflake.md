# Restore table after truncate
If you truncate a table on accident, just don't panic and [time travel](https://docs.snowflake.com/en/user-guide/data-time-travel.html)
```sql
TRUNCATE <my_table>; ---- oooppppsss I just truncated the wrong table !!!!
SELECT CURRENT_TIMESTAMP(); -- don't panic, just jot down the timestamp 2021-03-10 03:14:50.270 -0800

insert into <my_table>
select *
from <my_table>
at(timestamp => '2021-03-10 02:14:50.270 -0800'::timestamp_tz); -- note: 1h earlier than mistake
```
