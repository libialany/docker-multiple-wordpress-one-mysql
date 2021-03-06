# docker-multiple-wordpress-one-mysql
docker-compose sample for multiple wordpress

**SETUP**

``
cd docker-wordpress-3 
``

**modify init/01.sql**:

``
CREATE DATABASE <WORDPRESS_DB_1> DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
GRANT ALL ON <WORDPRESS_DB_1>.* TO '<WORDPRESS_USR>'@'%';
CREATE DATABASE <WORDPRESS_DB_2> DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
GRANT ALL ON <WORDPRESS_DB_2>.* TO '<WORDPRESS_USR>'@'%';
``

**like:**

``
CREATE DATABASE worddb DEFAULT CHARACTER SET utf8 COLLATE.....
#more
``

**with those values are in .env file**.
<code>
<p>..</p>
<p>    environment:</p>
<p>      WORDPRESS_DB_HOST: dbc</p>
<p>      WORDPRESS_DB_USER: ${WORDPRESS_USR}</p>
<p>      WORDPRESS_DB_PASSWORD: ${WORDPRESS_PASSWD}</p>
<p>      WORDPRESS_DB_NAME: ${WORDPRESS_DB_2}</p>
<p>..</p>
<p>    environment:</p>
<p>      .....</p>
<p>      WORDPRESS_DB_USER: ${WORDPRESS_USR}</p>
<p>      WORDPRESS_DB_PASSWORD: ${WORDPRESS_PASSWD}</p>
<p>      WORDPRESS_DB_NAME: ${WORDPRESS_DB_1}</p>
</code>


__RUN:__

``
docker-compose --env-file .env up
``


_**NOTE**_ : docker-compose-2 is just for explain in [All you need is docker-compose](https://medium.com/@elibialany/all-you-need-is-docker-compose-511f2a6fcab5)
