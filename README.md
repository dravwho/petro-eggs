# Pterodactyl Egg Collection (Updated)

A collection of updated Pterodactyl Panel eggs with the latest runtime and database versions.
Forked and updated from pelican-eggs/eggs (https://github.com/pelican-eggs/eggs).

---

## Runtime Eggs

| Runtime   | Version                           | File |
|-----------|-----------------------------------|------------------------------------------|
| Node.js   | 26 / 24 / 22 (LTS only)           | nodejs/egg-node-js.json |
| Python    | 3.15 / 3.14 / 3.13 / 3.12         | python/egg-python-generic.json |
| Bun       | 1.4 (Latest)                      | bun/egg-bun-generic.json |
| Deno      | 2.9 (Latest)                      | deno/egg-deno-generic.json |

## Database Eggs

| Database        | Version                    | Port  | File |
|-----------------|----------------------------|-------|------------------------------------------|
| MySQL           | 9.7 LTS / 8.4 LTS          | 3306  | database/egg-mysql.json |
| MariaDB         | 12.3 LTS / 11.8 / 11.4 / 10.11 | 3306 | database/egg-mariadb.json |
| PostgreSQL      | 18 / 17 / 16 / 15          | 5432  | database/egg-postgresql.json |
| MongoDB         | 9.0 / 8.3 / 8.0 / 7.0      | 27017 | database/egg-mongodb.json |
| Redis           | 8.10 / 7                   | 6379  | database/egg-redis.json |
| SQLite Web      | Python 3.15                | 8080  | database/egg-sqlite-web.json |

---

## Installation

1. Download the .json file for the egg you need.
2. Open your Pterodactyl Admin Panel.
3. Go to Nests, then select or create a nest.
4. Click Import Egg and upload the .json file.
5. Create a new server using the imported egg.

---

## What Changed (Nov 2026 Update)

### Runtime eggs
- **Node.js**: Dropped EOL versions (18/20/21/23). Only supported LTS remain (26/24/22).
- **Python**: Added 3.15 and 3.14. Removed 3.10 (EOL).
- **Bun**: Updated to 1.4 with latest runtime improvements.
- **Deno**: Updated to 2.9 series.

### Database eggs
- **MySQL**: Added 9.7 LTS as recommended (MySQL 8.4 remains available).
- **MariaDB**: Updated to 12.3 LTS (latest), plus 11.8 / 11.4 / 10.11 LTS branches.
- **PostgreSQL**: Kept 18–15 (PostgreSQL 14 reached EOL Nov 2026).
- **MongoDB**: Added 9.0, added 8.3, kept 8.0 & 7.0. Removed EOL rapid releases.
- **Redis**: Updated description for 8.10 series.

---

## Variables (Runtime Eggs)

| Variable        | Description                           | Default |
|-----------------|---------------------------------------|----------|
| MAIN_FILE       | Main file to run                      | index.js / main.py / index.ts |
| AUTO_UPDATE     | Pull latest git on startup (1 = on)   | 0 |
| GIT_ADDRESS     | Git repo URL                          | (empty) |
| BRANCH          | Git branch                            | master |
| USERNAME        | Git username for private repos        | (empty) |
| ACCESS_TOKEN    | Git token for private repos           | (empty) |
| USER_UPLOAD     | Skip git, use uploaded files (1 = on) | 0 |

## Variables (Database Eggs)

| Variable             | Description                          | Default |
|----------------------|--------------------------------------|-------------|
| MYSQL_ROOT_PASSWORD  | MySQL root password                  | changeme |
| MARIADB_ROOT_PASSWORD| MariaDB root password                | changeme |
| POSTGRES_PASSWORD    | PostgreSQL superuser password        | changeme |
| POSTGRES_DB          | Default database name                | mydb |
| REDIS_PASSWORD       | Redis auth password                  | changeme |
| MAX_MEMORY           | Redis max memory in MB               | 256 |
| EVICTION_POLICY      | Redis eviction policy                | allkeys-lru |
| CACHE_SIZE           | MongoDB WiredTiger cache size in GB  | 0.5 |
| DB_FILE              | SQLite database file name            | database.db |

---

## File Structure

```
ptero-eggs/
├── nodejs/
│   └── egg-node-js.json
├── python/
│   └── egg-python-generic.json
├── bun/
│   └── egg-bun-generic.json
├── deno/
│   └── egg-deno-generic.json
├── database/
│   ├── egg-mysql.json
│   ├── egg-mariadb.json
│   ├── egg-postgresql.json
│   ├── egg-mongodb.json
│   ├── egg-redis.json
│   └── egg-sqlite-web.json
└── README.md
```

---

## Changelog

**v1.3.0 - 2026-11-19**
- Major version bump for all runtimes and databases
- Node.js: only LTS versions (26/24/22)
- Python: 3.15 / 3.14 / 3.13 / 3.12
- Bun 1.4, Deno 2.9
- MySQL 9.7 LTS, MariaDB 12.3 LTS
- MongoDB 9.0
- Cleaned installation script comments
- Updated all descriptions and exported_at dates

**v1.2.0 - 2026-06-06**
- Added MySQL 8.4 egg
- Added MariaDB 11.7 egg
- Added PostgreSQL 18 egg
- Added MongoDB 8.2 egg
- Added Redis 8 egg
- Added SQLite Web Manager egg

**v1.1.0 - 2026-06-06**
- Added Bun 1.3 egg
- Added Deno 2.7 egg
- Added Python 3.13 egg
- Added Node.js 26 egg

**v1.0.0**
- Initial fork from pelican-eggs/eggs

---

## Note on Docker Images

Some docker images may not yet be available depending on parkervcp/yolks (now pelican-eggs/yolks) publish schedule.
If an image is unavailable, use the closest available version as a fallback.
Track image availability at: https://github.com/pelican-eggs/yolks

---

## Contributing

Pull requests are welcome. If an egg is outdated or you want to add a new runtime or database:

1. Fork this repo.
2. Create a branch: `git checkout -b add/name`
3. Commit: `git commit -m "add: egg for X vY"`
4. Open a Pull Request.

---

## License

MIT - Based on original work by pelican-eggs (https://github.com/pelican-eggs).
