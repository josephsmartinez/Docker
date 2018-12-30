# Assignment: Create Stack with Secrets

- Use the Drupal compose file from the last assignment
`(compose-assigment-2)`
- Rename image back to the official `drupal:8.2`
- Remove `build:`
- Add Secret via `external:`
- Use environment variable POSTGRES_PASSWORD_FILE
- Add secret via cli `echo <pwd> | docker secret create psql-pw -`
- Copy compose into a new yml file on your Swarm node1
