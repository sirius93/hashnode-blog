## How to Install and configure SonarQube with SonarScanner for generating sonar Report for your…

1\. Steps to Install SonarQube :

\* Go to [https://www.sonarqube.org/downloads/](https://www.sonarqube.org/downloads/) and click “Download LTS”

\* Once download is complete, Unzip your sonar file in your C or D drive.

\* Go to “{Your root path}\\sonarqube-6.7.1\\bin\\windows-x86–64” and click . on StartSonar.bat file.

It will start a Sonar server at “localhost:9000” , You can login to your Sonar with following preset credentials.  
 username : admin  
 password : admin

2\. Steps to Install Sonar-scanner :

\* Go to  
 [https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner) and click Windows 64 bit.

\* Once download is complete, Unzip the file and save it to your C or D drive.

\* You can set path variable for Sonar-scanner by adding **“{Your root path}\\sonar-scanner\\bin”** to your path

3\. Steps to Generate sonar Report:

\* Go to Your project’s root directory.

\* Execute the following command.

sonar-scanner -D sonar.projectKey="YOUR SONAR PROJECT KEY" -D sonar.sources=."PATH TO YOUR JAVASCRIPT SOURCE FOLDER" -D sonar.host.url=http://localhost:9000

4\. Configuring Your javascript Quality profile:

\* Once You are logged In, Click On Quality Profiles and then click dropdown button next to create.

\* Click Restore Profile and the import your custom JavaScript-profile XML, Browse the javascript profile & upload it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1653045730008/rXttQs3zR.png)