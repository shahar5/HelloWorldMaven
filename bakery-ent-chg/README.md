VM – 
Platform: AWS
Type: EC2
OS: Ubuntu 18.04 LTS
--------------------------------------
Commands –
1.	sudo apt-get install docker –y
2.	mkdir Jenkins_container
3.	touch Dockerfile
4.	nano Dockerfile -
** Screenshot **

5. sudo docker build -t jen-mav-co:2.0 .

6. docker run --publish 11000:8080 -d --name jen-mav-co2 --mount type=bind,source=/home/ubuntu/jenkins_container/workspace,target=/var/jenkins_home/jenkins-workspace jen-mav-co:2.0

7. sudo docker exec -it jen-mav-co2 cat /var/jenkins_home/secrets/initialAdminPassword

8. sudo docker exec -u 0 -it jen-mav-co2 bash

9. cd /var/jenkins_home/

10. nano config.xml

11. # edit workspace dir

** Screenshots **

12. # UI -> Manage Jenkins -> Reload Configuration from Disk

13. # check java home dir & mvn home dir
sudo docker exec -it jen-mav-co2 mvn --version

14. # set jave & maven home dirs
# UI -> Manage Jenkins -> Global Tool Configuration

** Screenshots **

15. # UI -> Manage Jenkins -> Manage Plugins -> install Pipeline Maven Intergration Plugin -> Install & Restart

16. # UI -> New Item -> Pipeline & give name -> Pipeline tab -> following configuration
** screenshot **

17. Build
** Screenshot **

18. Console Outpot log
** Attach log **







