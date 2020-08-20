VM – 
Platform: AWS
Type: EC2
OS: Ubuntu 18.04 LTS

Commands –

1.	sudo apt-get install docker –y
2.	mkdir Jenkins_container
3.	touch Dockerfile
4.	nano Dockerfile -
![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Dockerfile.PNG)

5. sudo docker build -t jen-mav-co:2.0 .

6. docker run --publish 11000:8080 -d --name jen-mav-co2 --mount type=bind,source=/home/ubuntu/jenkins_container/workspace,target=/var/jenkins_home/jenkins-workspace jen-mav-co:2.0

7. sudo docker exec -it jen-mav-co2 cat /var/jenkins_home/secrets/initialAdminPassword

8. sudo docker exec -u 0 -it jen-mav-co2 bash

9. cd /var/jenkins_home/

10. nano config.xml

11. # edit workspace dir
![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Workspace%20dir.png)

12. # UI -> Manage Jenkins -> Reload Configuration from Disk

13. # check java home dir & mvn home dir
sudo docker exec -it jen-mav-co2 mvn --version

14. # set jave & maven home dirs
 UI -> Manage Jenkins -> Global Tool Configuration
![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Java%20home%20dir.PNG)
![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Maven%20home%20dir.PNG)

15. # UI -> Manage Jenkins -> Manage Plugins -> install Pipeline Maven Intergration Plugin -> Install & Restart

16. # UI -> New Item -> Pipeline & give name -> Pipeline tab -> following configuration
![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Pipeline%20config.png)

17. Build
![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Success%20build.PNG)

18. Console Outpot log
[Console Outpot log](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Console%20Outpot%20log.txt)

19. Artifacts after build

![alt text](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/Artifacts%20after%20build.PNG)

[POM file](https://github.com/shahar5/HelloWorldMaven/blob/master/bakery-ent-chg/HelloWorldMaven-1.0.4-SNAPSHOT.pom)







