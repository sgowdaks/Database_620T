1. We can use redis https://try.redis.io/ for key value database (popular key value database)
2. In key -> value, if value data Type is structured then its called "wide column" 

# key value commands:
* `GET <key>` -> get the key
* `SET <key>`-> set the key
* `DEL <key>` -> delete key

Datbase application: 
events = [name, date, people] 
people = [id, name, email]


##event
* `SET id1 ids|Halim|Halim.com`
* `SET id2 id2|Waren|waren@bald.beautiful`
* `SET id3 id3|Garrett|garrett@physics.edu`

* `GET id2` -> "id2|Waren|waren@bald.beautiful"
* `KEY *` -> "id1", "id3", "id2" (keys returned are not in sequence, so database never stores it in sequence)

##people 





