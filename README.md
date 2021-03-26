# BCITLinuxproject
##Welcome to the coolest weather service
These files will create a cool weather text hourly on your machine

Here is the instruction tell you how to set my file to your linux
So that you can have a weather information like this: [wttr.in](http://wttr.in)


##Usage

###Choose a setting directory
1. After you clone my repo to your machine you need to choose a folder where the Script(wrr) run
   or just choose the current repo as your setting folder. 

2. The folder you choose will influence the settings in the .service file **make sure the path is
   exist.**

3. You can type `cp files folderyouwant` to copy and paste files to the selected folder

4. Type `ls folderpath` to check the selected folder has the files or not 

###Configure the .service file
1. Go to the folder where you copy files. Use `vim wttr.service` to change the content.

2. You will see one line code `ExecStart = /home/vagrant/week11/wrr`. Pressing **I** to insert mode
   change the path to the absolute path where wrr file currently in.

3. You can Type `pwd` outside to check the current path.

4. Change this line code `WorkingDirectory = /home/vagrant/week11` to be the same with the 2 step 
   **but without the Script name (wrr)**

5. Press `:` and type `wq` at the bottom to quit and save the file

###Move the file and run the service
1. Type `cp files /etc/systemd/system` move the wttr.service and wttr.timer to this folder **/etc/systemd/system**
   *You may use `sudo` in the front of cp if permission denied*

2. Type `ls /etc/systemd/system` to check the file exist in that folder

3. Type `sudo systemctl daemon-reload` reload the services

4. Type `sudo systemctl start wttr.service` to run the services

5. Type `sudo systemctl start wttr.timer` to run the services timer so the service can be triggered hourly

6. You can type `systemctl status wttr.service or timer` to check the running status of both file

7. If all the operations are correct, you will see a **weather.txt** created in `WorkingDirectory=path you typed`.
   Type `cat weather.txt` you will see the coolest weather information

###Set your service status
1. Type `sudo systemctl enable wttr.service` will let the service run when your machine start.
   You also need to do this for wttr.timer

2. Type `sudo systemctl disable wttr.service` will ban the service to run but you need to do this
   for the wttr.timer first.


Hope you enjoy my files   

 

