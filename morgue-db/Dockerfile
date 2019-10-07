FROM mariadb:latest

COPY schemas/postmortems.sql /docker-entrypoint-initdb.d/morgue01_postmortems.sql
COPY schemas/images.sql /docker-entrypoint-initdb.d/morgue02_images.sql
COPY schemas/jira.sql /docker-entrypoint-initdb.d/morgue03_jira.sql
COPY schemas/links.sql /docker-entrypoint-initdb.d/morgue04_links.sql
COPY schemas/irc.sql /docker-entrypoint-initdb.d/morgue05_irc.sql
COPY schemas/slack.sql /docker-entrypoint-initdb.d/morgue06_slack.sql
COPY schemas/anniversary.sql /docker-entrypoint-initdb.d/morgue07_anniversary.sql
