initiate the DB as:

    docker run --rm sentry config generate-secret-key

    docker run -it --rm -e SENTRY_SECRET_KEY='ul9j2sdsvdt_*9mp&hl_mc6*4&7kklj=xhj1kfv=p(75u4=q=' -e SENTRY_REDIS_PORT=`dig _redis.sentry._tcp.marathon.mesos SRV | grep -A1 'ANSWER SECTION' | cut -f5 -d ' ' | tail -1` -e SENTRY_REDIS_HOST=`host redis.sentry.marathon.mesos | cut -f 4 -d ' '` -e SENTRY_POSTGRES_HOST=`host postgres.sentry.marathon.mesos | cut -f 4 -d ' '` -e SENTRY_POSTGRES_PORT=`dig _postgres.sentry._tcp.marathon.mesos SRV | grep -A1 'ANSWER SECTION' | cut -f5 -d ' ' | tail -1` -e SENTRY_DB_NAME=postgres -e SENTRY_DB_USER=sentry -e SENTRY_DB_PASSWORD=secret sentry upgrade


