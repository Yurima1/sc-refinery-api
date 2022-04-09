# SC-REFINERY-API

API for cooperative Mining Management in Star Citizen.
See also frontend app: github.com/fre-sch/sc-refinery-app


## Configure

Copy ``dist/example.config.yml`` to ``config.yml`` and edit values.
Create initial admin user using the command line.


## Run local development mode

Create configuration as above.

Create ``.env`` file with contents:

```
CONFIG_PATH=config.yml
PYTHONPATH=.
PIPENV_VERBOSITY=-1
```

Start server using:

```bash
uvicorn screfinery.main:app --reload --debug --log-level=error
```


## Command line

Requires environment variable ``CONFIG_PATH`` to point to ``config.yml``.

```bash
python screfinery/cli.py --help
```

Dump database schema:
```bash
python screfinery/cli.py dump-schema
```

Create a new user:
```bash
python screfinery/cli.py user create admin "email address" "admin_password" "*,admin"
```