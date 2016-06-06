

git remote add origin https://github.com/TimColpo/TestRepository.git


1) Make a local folder
2) Create a test file like README.md
3) Have a git Account setup and a URL

C:\Programs\data>dir
 Volume in drive C is OSDisk
 Volume Serial Number is 7417-3516

 Directory of C:\Programs\data

06/03/2016  13:10    <DIR>          .
06/03/2016  13:10    <DIR>          ..
06/03/2016  13:08    <DIR>          git
06/03/2016  13:10                 9 README.md
               1 File(s)              9 bytes
               3 Dir(s)  20,760,735,744 bytes free


C:\Programs\data>git init
Initialized empty Git repository in C:/Programs/data/.git/

C:\Programs\data>git add README.md

C:\Programs\data>dir
 Volume in drive C is OSDisk
 Volume Serial Number is 7417-3516

 Directory of C:\Programs\data

06/03/2016  13:14    <DIR>          .
06/03/2016  13:14    <DIR>          ..
06/03/2016  13:08    <DIR>          git
06/03/2016  13:10                 9 README.md
               1 File(s)              9 bytes
               3 Dir(s)  20,760,698,880 bytes free

C:\Programs\data>git commit -m "first commit"
[master (root-commit) a6ef2cf] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

C:\Programs\data>git remote add origin https://github.com/TimColpo/TestRepository.git

C:\Programs\data>git push -u origin master
Username for 'https://github.com': TimColpo
Password for 'https://TimColpo@github.com':
Counting objects: 3, done.
Writing objects: 100% (3/3), 227 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/TimColpo/TestRepository.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.


On GIT Generate Token

55a9fd7c43472f53eb22c62c9282c4c1af15bdf0



Donload the Splunk GITBUB ZIP

Install to SPlunk

SCP

pscp -i C:\Users\timothy.a.colpo\Desktop\AAA_Tim\Customers\Disney\na-stanleykaplunov.ppk C:\Users\timothy.a.colpo\Desktop\AAA_Tim\Customers\Disney\Splunk\applications\github-modular-input_100.tgz ec2-user@52.87.235.25:/home/ec2-user

on the server


tar -xsvf github-modular-input_100.tgz
subo mv github-modinput /opt/splunk/etc/apps
sudo chown splunk:splunk /opt/splunk/etc/apps/github-modinput

on UI

Add Index github-demo2





###
## SERVICENOW
###

tar -xsvf splunk-app-for-servicenow_401.tgz

tar -xvsf splunk-add-on-for-servicenow_280.tgz

###
## DBCONNECT FOR JENKINS
###

tar -xsvf splunk-db-connect-2_220


[splunk@ip-10-0-0-175 local]$ cat inputs.conf
[rpcstart://default]
javahome = /usr/lib/jdk1.8.0_77
useSSL = 0
proc_pid = 16619

[mi_input://stats_job]
connection = CICD_stats
index = jenkins_mysql
input_timestamp_column_name = last_updated
interval = 3600
max_rows = 100000
mode = tail
output_timestamp_format = yyyy-MM-dd HH:mm:ss
query = SELECT * FROM `jenkins_data`.`stats_job`
source = jenkins
sourcetype = jenkins_mysql
tail_follow_only = 1
tail_rising_column_name = last_updated
ui_query_catalog = jenkins_data
ui_query_mode = simple
ui_query_schema = NULL
ui_query_table = stats_job
tail_rising_column_checkpoint_value = 2016-05-20 06:24:04.0
[splunk@ip-10-0-0-175 local]$
