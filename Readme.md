# Run dev mode
```
docker-compose up -d --build
docker-compose exec web python manage.py migrate --noinput
```

## Stop dev mode
```
docker-compose down -v
```


# Run prod mode
```
docker-compose -f docker-compose.prod.yml up -d --build
docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
docker-compose -f docker-compose.prod.yml down -v
docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear

```