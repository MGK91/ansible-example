# ansible-example

   22  ansible all -m ping -i host.ini 
   24  ansible all -m ping -i host.ini 
   25  ansible all -a "uptime"  -i host.ini 
   26  ansible app  -a "uptime"  -i host.ini 
   28  ansible app  -a "which python"  -i host.ini 
   29  ansible app  -a "which python3"  -i host.ini 
   30  ansible app  -a "ps -ef|grep java"  -i host.ini 
   31  ansible web -m yum "name=nginx state=present"  -i host.ini 
   32  ansible web -m yum -a "name=nginx state=present"  -i host.ini 
   33  ansible web -m yum -a "name=nginx state=present"  -b -i host.ini  
   37  ansible app -m yum -a "name=java-11-openjdk-devel state=present"  -b -i host.ini  
   41  ansible app -m yum -a "name=tomcat state=present"  -b -i host.ini  
   44  ansible web -m copy -a "src=./index.html dest=/var/www/html" -b -i host.ini 
   45  ansible app  -a "mkdir -p /var/www/html"  -i host.ini 
   46  ansible web  -a "mkdir -p /var/www/html" -b  -i host.ini 
   47  ansible web -m copy -a "src=./index.html dest=/var/www/html" -b -i host.ini 
   48  ansible web  -a "rm -rf  /var/www/html/index.html" -b  -i host.ini 
   49  ansible web -m copy -a "src=./index.html dest=/var/www/html owner=ec2-user group=ec2-user mode=0644" -b -i host.ini 
   53  ansible web -m fetch -a "src=/var/www/html/index.html dest=./" -b -i 
   54  ansible web -m fetch -a "src=/var/www/html/index.html dest=./" -b -i host.ini 
   60  ansible web -m service -a "name=nginx state=restarted" -b  -i host.ini 
   65  ansible web -m service -a "name=nginx state=restarted" -b  -i host.ini 
   66  ansible web -m group -a "name=nginx state=present" -b  -i host.ini 
   67  ansible web -m user -a "name=nginx group=nginx shell=/bin/bash state=present" -b  -i host.ini 
   68  ansible web -a "id nginx" -b -i host.ini 
   72  ansible web -m copy -a "src=./index.html dest=/var/www/html owner=nginx group=nginx mode=0644" -b -i host.ini 
