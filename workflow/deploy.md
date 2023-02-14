# Deploy

1. SSH to EC2
    ````bash
    ssh -i "C:\Users\<username>\.ssh\ec2-web-ubuntu-server.pem" ubuntu@ec2-54-169-157-218.ap-southeast-1.compute.amazonaws.com
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218781077-27c52a2d-2a4f-4fa8-b947-255046d6f324.png)

2. Switch to web user, change to project directory
    ````bash
    sudo su web
    cd ~/app-project-dev
    ````
    
3. Putting the system down
    ````bash
    php artisan down
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218782639-8d55cf2e-53aa-4b4b-952a-fafb9c1eff9c.png)

4. Pull the code change
    ````bash
    git pull origin dev
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218783689-ad8a249b-4588-4a95-8be4-dff5267f934f.png)

    
5. Install dependencies
    ````bash
    composer install --no-interaction
    # or
    composer install --no-interaction
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218783966-84a28e38-ad0e-4654-9363-292f0b4478c4.png)

6. Database changes
    ````bash
    php artisan migrate
    
    # run seeder, optional
    php artisan db:seed --class=SeederClass
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218785135-e91ff3f8-5058-4916-989a-e04dc01d53a0.png)

7. Environment changes
    ````bash
    # Manualy update .env key/value, optional
    nano .env
    ````
    
8. Restart what needs to be restarted, and clean what should be cleaned
    ````bash
    php artisan cache:clear
    php artisan route:clear
    php artisan view:clear
    
    sudo su
    echo "" | sudo -S service php8.1-fpm reload
    
    # Restart Queue
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218787624-c3fc2126-b15b-4ea6-901e-08d2ed5e6b97.png)
    ![image](https://user-images.githubusercontent.com/103056751/218788204-14fc09ee-0ee5-4489-bc78-e580c320b6d3.png)
  
9. Go UP
    ````bash
    php artisan up
    ````
    ![image](https://user-images.githubusercontent.com/103056751/218787339-61c31dd9-a4d4-49f2-a899-fde4a5ef1140.png)
