# MathHub

The new version of the MathHub System, managed with Docker Compose. 

## Usage

```bash
# Set a secret key which is used by the admin interface for login
# Change some-super-secret-string to some secret
echo "DJANGO_SECRET_KEY=some-super-secret-string" > .env

# to start all the containers
docker-compose up -d

# to create an initial admin user
docker-compose exec admin python manage.py createsuperuser

# to stop the containers
docker-compose down
```