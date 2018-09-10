### Howtos

#### The Docker Setup
##### Add Host Adress to your /etc/hosts
    echo -e "0.0.0.0 app.doc" | sudo tee -a /etc/hosts

##### Get Git Repository
    git clone git@github.com:aliuosio/docker-lamp.git

##### start docker first time (!! on OSX !!)
    sudo chmod -R 777 app_root/
    cd .docker
    docker-sync start
    docker-compose -f docker-compose.mac.yml up -d

##### start docker first time (!! on NONE OSX !!)
    sudo chmod -R 777 app_root/
    cd .docker
    docker-compose up -d
    
#### after first run (on the everyday bases)
    cd .docker
    docker-compose start
    
##### Login to PHP container
    docker exec -it app_php_<version> bash
    
##### Login to Web Server container
    docker exec -it app_webserver bash
    
##### Use Composer
    docker exec -it app_php_<version> composer <command>
    
##### Connect Sequel to MySQL
    Host: 0.0.0.0
    User: root
    Password: root
    
##### All outgoing mails are sent to MailHog
    http://app.doc:8025
