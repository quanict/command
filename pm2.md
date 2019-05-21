http://pm2.keymetrics.io/docs/usage/cluster-mode/

# Log management

http://pm2.keymetrics.io/docs/usage/log-management/#flushing-logs

## Displaying logs in real-time

>>Display option for pm2 logs command

    pm2 logs -h

### Display all apps logs

    pm2 logs

### Display only logs about process containing "api" in their name

    pm2 logs /api/

### It's a regex so you can filter with the normal syntax to filter with OR condition

    pm2 logs /server_[12]/

### Display only api app logs

    pm2 logs api

### Display X lines of api log file

    pm2 logs big-api --lines 1000

## Flushing logs

    pm2 flush # Clear all the logs

## Rotating Logs

    pm2 install pm2-logrotate