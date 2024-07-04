# MarketPeak_Ecommerce
I created a project directory named "MarketPeak_Ecommerce and in this directory, i initialize a git repository in it with the following commands: mkdir MarketPeak_Ecommerce

cd MarketPeak_Ecommerce

git init

To download a website template, i visited "Tooplate" and downloaded the specitic template (2130_waso_strategy). I then extracted the template into my project directory "MarketPeak_Ecommerce" to prepare the website template.

Using "git add .", I added the website files to my git repository. Then I configured both my user name and user email with the next 2 commands:

git config --global user.name "Centinno88"

git config --global user.email "Innocentuzomba88@gmail.com"

I commit the changes with this command: git commit -m "Initial commit with basic e-commerce site structure"

For version control and collaboration, I pushed the code to a remote repository on the Github with the following steps:

I logged into my github accounct and created a new empty repository named "MarketPeak_Ecommerce
I linked my local repository to Github by running this command:
git remote add origin https://github.com/Bettymusari/MarketPeak_Ecommerce.git

I then tried to push my commits to Github with "git push -u origin main" . It didn't work, so i went back to Github and used the process commands outlined:

echo "# MarketPeak_Ecommerce" >> README.md

git init

git add README.md

git commit -m "first commit"

git branch -M main

git add .

git push -u origin main :

This was successful wit the following result:

"Enumerating objects: 42, done. Counting objects: 100% (42/42), done. Delta compression using up to 4 threads Compressing objects: 100% (40/40), done. Writing objects: 100% (42/42), 1.85 MiB | 41.00 KiB/s, done. Total 42 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0) remote: Resolving deltas: 100% (1/1), done. To https://github.com/Centinno88/MarketPeak_Ecommerce.git

[new branch] main -> main branch 'main' set up to track 'origin/main'."
AWS Deployment:

On my AWS Management Console, I launched an instance named "MarketPeak_Ecommerce" on an AWS Linux AMI I connected to the instance using SSH I then cloned the Github repository to my AWS EC2 instance with the following steps: On my EC2 instance, i generated an SSH key using "ssh-keygen" Then I displayed and copied my public key with this command: "cat /home/ubuntu/.ssh/id_rsa.pub" I then added my SSH public key to my Github account. I used the SSH clone URL to clone the repository:

"git clone git@github.com:yourusername/MarketPeak_Ecommerce.git"

I installed Apache web server on my EC2 instance with:

sudo yum update -y

sudo yum install httpd -y

sudo systemctl start httpd

sudo systemctl enable httpd

I then configured the httpd for the website using:

sudo rm -rf /var/www/html/*

sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/

To apply the changes, I reloaded the server with: "sudo systemctl reload httpd"

With this, my Marketpeak-Ecormmerce Platform went live and can be accessed via: http://3.133.15.134/2130_waso_strategy/

For Continous Deployment and Integration Workflow, I created a new branch named "development" and navigated to it with the following commands:

"git branch development"

"git checkout development"

In the index.html I made a change to the title. I changed the title from "waso strategy" to "MarketPeak_Ecomerce"

Using "git add ." I staged the changes

I then commit the stage with: "git commit -m "Add new features or fix bugs" Then pushed the changes to Github : 'git push origin development". This gave the result below:

Admin@DESKTOP-QI6H2EA MINGW64 ~/Desktop/MarketPeak_Ecommerce (development) Enumerating objects: 7, done. Counting objects: 100% (7/7), done. Delta compression using up to 4 threads Merge branch 'development' Compressing objects: 100% (4/4), done. Writing objects: 100% (4/4), 402 bytes | 201.00 KiB/s, done. Total 4 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0) remote: Resolving deltas: 100% (2/2), completed with 2 local objects. To https://github.com/Centinno88/MarketPeak_Ecommerce.git e0bf174..d7c4e67 development -> development

I then created a Pull Request on Github, reviewed and then merged the changes using the following commands: "git checkout main" and "git merge development" The results are as follows:

Admin@DESKTOP-QI6H2EA MINGW64 ~/Desktop/MarketPeak_Ecommerce (development) $ git checkout main Switched to branch 'main' Your branch is up to date with 'origin/main'.

Admin@DESKTOP-QI6H2EA MINGW64 ~/Desktop/MarketPeak_Ecommerce (main) $ git merge development Merge made by the 'ort' strategy. 2130_waso_strategy/index.html | 2 +- 1 file changed, 1 insertion(+), 1 deletion(-)

I pushed the merged changes to Github through the main with the result below:

Admin@DESKTOP-QI6H2EA MINGW64 ~/Desktop/MarketPeak_Ecommerce (main) $ git push origin main Enumerating objects: 1, done. Counting objects: 100% (1/1), done. Writing objects: 100% (1/1), 244 bytes | 244.00 KiB/s, done. Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0) To https://github.com/Centinno88/MarketPeak_Ecommerce.git 64a4931..20a9a25 main -> main

Deploying Updates to the Production Server;

I tried this code "git pull origin main" on my instance, and it came back with an error message. [ec2-user@ip-172-31-2-104 ~]$ git pull origin main fatal: not a git repository (or any of the parent directories): .git

I tried the following steps : No success [ec2-user@ip-172-31-2-104 ~]$ ls /var/www/html 2130_waso_strategy README.md [ec2-user@ip-172-31-2-104 ~]$ ls /var/www/html/2130_waso_startegy ls: cannot access '/var/www/html/2130_waso_startegy': No such file or directory [ec2-user@ip-172-31-2-104 ~]$ git clone https://github.com/Ceninno88/MarketPeak_Ecommerce.git fatal: destination path 'MarketPeak_Ecommerce' already exists and is not an empty directory. [ec2-user@ip-172-31-2-104 ~]$ cd /var/www/html/2130_waso_strategy [ec2-user@ip-172-31-2-104 2130_waso_strategy]$ git pull origin main fatal: not a git repository (or any of the parent directories): .git

I thought git wasn't installed and i tried to install, but found it already installed: [ec2-user@ip-172-31-2-104 2130_waso_strategy]$ sudo yum install git -y Last metadata expiration check: 1 day, 6:12:52 ago on Fri May 31 08:48:36 2024. Package git-2.40.1-1.amzn2023.0.3.x86_64 is already installed. Dependencies resolved. Nothing to do. Complete!

Tried again to pull from home directory but failed again: [ec2-user@ip-172-31-2-104 2130_waso_strategy]$ cd ~ [ec2-user@ip-172-31-2-104 ~]$ git pull origin main fatal: not a git repository (or any of the parent directories): .git [ec2-user@ip-172-31-2-104 ~]$ git pull fatal: not a git repository (or any of the parent directories): .git

Ran ls to check the home directory [ec2-user@ip-172-31-2-104 ~]$ ls MarketPeak_Ecommerce

Ran ls MarketPeak_Ecommerce [ec2-user@ip-172-31-2-104 ~]$ ls MarketPeak_Ecommerce 2130_waso_strategy README.md

cd into MarketPeak_Ecommerce [ec2-user@ip-172-31-2-104 ~]$ cd MarketPeak_Ecommerce/

Then I ran "git pull" and was successful. [ec2-user@ip-172-31-2-104 MarketPeak_Ecommerce]$ git pull remote: Enumerating objects: 22, done. remote: Counting objects: 100% (22/22), done. remote: Compressing objects: 100% (9/9), done. remote: Total 17 (delta 8), reused 15 (delta 7), pack-reused 0 Unpacking objects: 100% (17/17), 3.69 KiB | 540.00 KiB/s, done. From github.com:Bettymusari/MarketPeak_Ecommerce 5274a76..20a9a25 main -> origin/main

[new branch] development -> origin/development Updating 5274a76..20a9a25 Fast-forward 2130_waso_strategy/index.html | 2 +- 2130_waso_strategy/project-detail.html | 2 +- README.md | 106 +++++++++++++++++++++++++++++++++ 3 files changed, 108 insertions(+), 2 deletions(-)
cd back to home: "cd ~" [ec2-user@ip-172-31-2-104 MarketPeak_Ecommerce]$ cd ~

Then ran the below command without sudo and failed:

[ec2-user@ip-172-31-2-104 ~]$ cp -r ~/MarketPeak_Ecommerce/2130_waso_strategy /var/www/html cp: cannot create regular file '/var/www/html/2130_waso_strategy/css/bootstrap-icons.css': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/css/bootstrap.min.css': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/css/magnific-popup.css': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/css/tooplate-waso-strategy.css': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/jason-goodman-MUZFKa_mttU-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/peter-jones-WZROBIlY8Rg-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/services/portrait-smiling-african-american-young-woman-holding-movie-production-blackboard.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/services/startup-leader-drawing-flowchart-board-discussing-project.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/services/young-entrepreneurs-mature-investor-watching-presentation-discussing-project.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/projects/elena-baidak-pz69kY0UQuQ-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/projects/evangeline-shaw-nwLTVwb7DbU-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/projects/pj-gal-szabo-CIXXIWxxec4-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/projects/tangerine-newt-AKH4OVEmILc-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/projects/team-fredi-FN3vmVee2sI-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/projects/vmsign-x9yGe7wnvKQ-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/slide/christina-wocintechchat-com-NDoVgcS_lZM-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/images/slide/jason-goodman-0K7GgiA8lVE-unsplash.jpg': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/bootstrap.min.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/click-scroll.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/custom.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/jquery.magnific-popup.min.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/jquery.min.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/jquery.sticky.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/js/magnific-popup-options.js': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/ABOUT THIS TEMPLATE.txt': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/fonts/bootstrap-icons.woff': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/fonts/bootstrap-icons.woff2': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/index.html': Permission denied cp: cannot create regular file '/var/www/html/2130_waso_strategy/project-detail.html': Permission denied

Then I ran the command again with sudo and succeeded [ec2-user@ip-172-31-2-104 ~]$ sudo cp -r ~/MarketPeak_Ecommerce/2130_waso_strategy /var/www/html

Lastly, I reloaded my remote server successfully with the below command: [ec2-user@ip-172-31-2-104 ~]$ sudo systemctl reload httpd

To test the changes, I pasted my ip address in my browser and comfirmed the changes made to the index.html file.

Public ip address:http://3.133.15.134/2130_waso_strategy/

In the main, all process documentation recorded in the README.md, staged, commit and also pushed to the Github repository.

CAPSTONE -INTRODUCTION_TO_CLOUD_COMPUTING PROJECT COMPLETED
