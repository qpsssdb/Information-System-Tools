# 4 лабораторная работа
В данной работе надо было сделать много заданий с докером (который четырежды вылетал, поэтому теперь я все буду записывать :с ).  
### задание 2
``` sql
select name Name from discussion_group where approve_required=true;
```
### задание 3
``` sql
select greatest(message_id, user_from_id, user_to_id) "ID",
    -> date(read_time) "READ", date(send_time) SEND, message_text TEXT
    -> from user_private_message where send_time between '2020-11-01' and '2020-11-30'
    ->  and message_text like'A%' and read_time  < adddate(send_time, interval +10 day);
```
### задание 4
``` sql
select min(joined_time), max(approved_time), count(*)
    -> from users_to_discussion_groups where approved=1;
```
### задание 5
``` sql
select user_id, registration_time from user order by registration_time desc limit 20;
```
### задание 6
``` sql
with groups_with_approve as (select * from discussion_group where approve_required=1), new_groups as
    -> (select * from groups_with_approve where creation_time>'2020-01-01') select * from  new_groups;
```
### задание 7
``` sql
with groups_with_approve as (select * from discussion_group where approve_required=1), new_groups as
    -> (select * from groups_with_approve where creation_time>'2020-01-01') select * from  new_groups;
```
### задание 8
``` sql
 with cntsum as (select date(send_time) time ,  user_from_id, count(1) as cnt from
    -> user_private_message group by date(send_time), user_from_id)
    ->  select count(*) user, sum(cnt) message, time from cntsum group by time having user=message;
```
### задание 9
```sql

```