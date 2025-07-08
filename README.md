# Perl Catalyst/Docker Starter

## Usage

```bash
docker compose up
```

The first time this app runs, as per `docker-compose.yml`, it will run `dummy.pl`, a script that doesn't do anything, but keeps the server alive. This allows us to create the actual application, for example: 

```bash
docker compose exec catalyst_app_server exec catalyst.pl MyApp
```

Then change in `docker-compose.yml`

```
command: "./dummy.pl"
```

to something like:

```
command: "./MyApp/script/myapp_server.pl --restart"
```

In order to actually run the app moving forward

Note: you will probably need to change ownership of the files created by the container in the `src` folder

```bash
sudo chown -R <your_username>:<your_username> src/
```

Based on [freehackquest/perl-catalyst](https://github.com/freehackquest/perl-catalyst/)