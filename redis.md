
Returns all keys matching pattern

	KEYS *
	KEYS *name*
	
	
#DEL key [key ...]
Removes the specified keys. A key is ignored if it does not exist.
```
> SET key1 "Hello"
"OK"
> SET key2 "World"
"OK"
> DEL key1 key2 key3
(integer) 2
> 
 ```
    