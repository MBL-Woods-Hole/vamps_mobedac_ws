# vamps_mobedac_ws
VAMPS based web service to handle mobedac requests

-- START server --
source /groups/vampsweb/vamps/seqinfobin/vamps_environment.sh
cd; . ~/python_setup_mobedac.sh; cd /usr/local/www/vamps/projects/mobedac_ws/deployments/current; python mobedac_server.py ws.ini production

-- STOP all threads --
do it in a browser:
http://vamps.mbl.edu/mobedac_ws/stop_the_server

-- CHANGE the code --
1) git on local:
git add . 
git commit -m "notes"
git pull origin master
git push origin master  

2) change db on VAMPS if needed (submission, submission_details, vamps_projects_datasets_pipe)

3) local:
cap vamps_production deploy:update

4) in a browser:
http://vamps.mbl.edu/mobedac_ws/stop_the_server

5) on VAMPS: 
(. ~/python_setup_mobedac.sh)
/usr/local/www/vamps/projects/mobedac_ws/deployments/current$ python mobedac_server.py ws.ini production 
or python mobedac_server.py ws.ini test
