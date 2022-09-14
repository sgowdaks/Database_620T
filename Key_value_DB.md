1. We can use redis https://try.redis.io/ for key value database (popular key value database)
2. In key -> value, if value data Type is structured then its called "wide column" 

# key value commands:
* `GET <key>` -> get the key
* `SET <key>`-> set the key
* `DEL <key>` -> delete key

Datbase application: 
events = [name, date, people] 
people = [id, name, email]


## event
* `SET id1 ids|Halim|Halim.com`
* `SET id2 id2|Waren|waren@bald.beautiful`
* `SET id3 id3|Garrett|garrett@physics.edu`

* `GET id2` -> "id2|Waren|waren@bald.beautiful"
* `KEY *` -> "id1", "id3", "id2" (keys returned are not in sequence, so database never stores it in sequence)

## people 
* `SET id4 sleep|2022-09-16|id2,id3`
* `GET id4` -> "sleep|2022-09-16|id2,id3"
* `KEY *` -> "id1", "id3", "id2" , "id4"
* `SET id5` -> "seaver 50th|2022-09-06|id1, id2, id3"
* `KEY *` -> "id1", "id3", "id2" , "id4", "id5"
* `KEYS *5` -> "id5"
* `GET id1, id2, id3` -> get with comma seperated is not possible
* `SET person-id3 id3|Garrett|garrett@physics.edu` 
* `SET person-id2 id2|Waren|waren@bald.beautiful` 
* `SET person-id2 ids|Halim|Halim.com`` 
* `SET event-id4 sleep|2022-09-16|id2,id3`
* `SET event-id5 seaver 50th|2022-09-06|id1, id2, id3`
* `KEY *` -> "person id3", "event-id4", "id2", "id3", "id1", "id4", "id5", "event-id5", "person id1", "person id2"
* `KEYS person-*` -> "person id3", "person id1", "person id2"
* `KEYS event-*` -> "event-id4", "event-id5"
* `DEL id1`
* `DEL id2`
* `DEL id3`
* `KEYS *` -> "event-id4", "event-id5", "person id3", "person id1", "person id2" (now we know which are all the event and which all are people)





