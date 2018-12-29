## Writing a Compose File

- Build a basic compose file for a Drupal content management system website. Docker Hub has information.
- Use the drupal image along with the postgres image.
- Use ports to expose Drupal on 8080 so you can connect to localhost:8080
- Be sure to set POSTGRES_PASSWORD for postgres
- Walk through Drupal setup via browser
- Tip: Drupal assumes DB is localhost, but it's service name.
- Use volumes to store Drupal unique data.
