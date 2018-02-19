# Video Server Streaming Configuration
A RESTful web service is implemeted using jersery in java platform in order to make API calls that add and remove streams from all the servers in the Video Server cluster.


## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. This project is tested on Ubuntu 16.04 machines.

### Prerequisites
Install Java, Tomcat7 and Eclipse for Java EE developers
```
sudo apt-get install default-jdk
sudo apt-get install tomcat7
sudo apt-get install tomcat7-docs tomcat7-examples tomcat7-admin
tar -zxvf eclipse-jee-mars-2-linux-gtk-x86_64.tar.gz -C /usr/
ln -s /usr/eclipse/eclipse /usr/bin/eclipse
```

### Build and test the project
→ Import the project WebService-for-VideoServer into eclipse

→ Set Tomcat7 as the target Runtime enviroment

→ Build the project as a Maven build

→ Run the project on tomcat7 server.

### Deploying the project
→ In Eclipse, right click on a Web project and select Export. Then select WAR file in the Export window and then select Next. Choose the project, the .war file name and folder to export. 

→ Place your .war file in /var/lib/tomcat7/webapps folder.

→ Restart the tomcat7 server.

### API Examples
To add streams
```
curl -X POST -H "no-check:true" -H "pwd:admin@123" "http://10.156.14.21:8086/VideoServerConfig/videostream?id=cam_123&playurl=rtsp://10.156.14.130:554/live.sdp"
```

To remove streams
```
curl -X DELETE -H "no-check:true" -H "pwd:admin@123" "http://10.156.14.21:8086/VideoServerConfig/videostream?id=cam_123"
```
