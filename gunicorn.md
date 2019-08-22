# gunicorn

## run

```
gunicorn --bind 0.0.0.0:8000 app:app
```

gunicorn --worker-class gevent --log-level debug --bind 0.0.0.0:8080 app
gunicorn --log-level debug --bind 0.0.0.0:8080 app


## start 

```
gunicorn app:app -b 0.0.0.0:8000 &
```

## stop gunicorn

```
pkill -f gunicorn
```

----
[doc]: http://docs.gunicorn.org/en/stable/deploy.html

[01]: http://docs.gunicorn.org/en/stable/run.html