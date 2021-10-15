Wordpress MYSQL integration with Docker
===

Ad hoc commands :
    
    # docker network create -d bridge dev-network --subnet=10.240.0.0/16

    # docker volume create mysql-dev-volume

    # docker volume create wordpress-dev-volume

    # docker container run -itd -e MYSQL_ROOT_PASSWORD=root \
    -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -e MYSQL_DATABASE=dev \
    -v mysql-dev-volume:/var/lib/mysql --network dev-network --name mysql-dev-db mysql

    # docker container run -itd -e WORDPRESS_DB_HOST=mysql-dev-db \
    -e WORDPRESS_DB_USER=admin -e WORDPRESS_DB_PASSWORD=admin -e WORDPRESS_DB_NAME=dev \
    -p 8080:80 --network dev-network --name wordpress-dev-app wordpress
    
___

Docker Compose
---
Deploy entire application stack with docker compose

    # docker-compose up
    
Delete entire application 
    
    # docker-compose down
    
___

Other resources :

[Docker installation on RedHat/Centos distros](https://www.linkedin.com/posts/pradeep-kumar-a68a9418b_docker-containerization-redhatenterpriselinux-activity-6848920877149642752-XmDf)
