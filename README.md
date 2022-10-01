version: '3.3'

services:

  live-pro-db:
    image: mysql:5.6
    
    
    environment:
      MYSQL_USER: wasim_notification
      
      MYSQL_ROOT_PASSWORD: Mobiloitte@1

    entrypoint:
      sh -c "
        echo 'CREATE DATABASE IF NOT EXISTS wasim_notidication; CREATE DATABASE IF NOT EXISTS wasim_static; CREATE DATABASE IF NOT EXISTS wasim_stripe_payment; CREATE DATABASE IF NOT EXISTS wasim_user_service; CREATE DATABASE IF NOT EXISTS wasim_wallet;' > /docker-entrypoint-initdb.d/init.sql;
        /usr/local/bin/docker-entrypoint.sh --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
      "
    ports:
      - 3307:3306 
   
