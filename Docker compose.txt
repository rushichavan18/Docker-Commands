services:
  mysql:
    image: mysql:5.7
    container_name: mysql
    environment:
      MYSQL_PASSWORD: admin
      MYSQL_USER: admin
      MYSQL_ROOT_PASSOWRD: admin
      MYSQL_DATABASE: tws_db

      volumes:
        - ./mysql_data_new:/var/lib/mysql

      networks:
        - twotier

      ports:
        - "3306:3306"

      healthcheck:
        test: ["CMD","mysqladmin","ping","-h","localhost","-uroot","-padmin"]
        interval: 10s
        retries: 5
        start_period: 60s
        timeout: 5s


    flaskapp:
      build:
        context: .
        container_name: flaskapp
        environment:
          MYSQL_HOST: mysql
          MYSQL_USER: root
          MYSQL_PASSOWRD: admin
          MYSQL_DB: tws_db

      networks:
        - twotier

      ports:
        - "5000:5000"

      depends_on:
          - mysql

volumes:
mysql_data_new:

networks:
  twotier:

