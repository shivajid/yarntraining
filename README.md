### yarntraining

 - yarn node -list -all
 - hdfs dfsadmin -report | more
 - yarn application -status <Application ID>
  $ yarn applicationattempt -list <Application ID>
  $ yarn applicationattempt -status <Application Attempt ID>
  $ yarn container -list <Application Attempt ID>
  $ yarn container -status <Container ID>


-rw-r--r-- 1 root root 32495 Feb 1 02:19 hadoop-yarn- applications-distributedshell-2.2.0.2.0.11.0-1.jar

yarn org.apache.hadoop.yarn.applications.distributedshell.Client -jar /usr/hdp/2.3.2.0-2950/hadoop-yarn/hadoop-yarn-applications-distributedshell-2.7.1.2.3.2.0-2950.jar -shell_command cal
￼
 
RuntheJobinTwoContainers
5.1. The DistributedShell application allows you to specify how many containers that the ApplicationMaster uses. Add the following arguments to your previous DistributedShell command:
-num_containers 8 -container_memory 20

Now view the aggregated log file:
# yarn logs -applicationId application_id
You should see 8 calendars this time - one from each container.
￼
NOTE: Look carefully at the log file of your previous application. Notice that the job executed with 9 Containers. One container was the ApplicationMaster, and the other 8 Containers executed the “cal” command.
￼￼￼￼￼￼￼￼￼


yarn rmadmin [-refreshQueues]
               [-refreshNodes]
               [-refreshUserToGroupsMapping] 
               [-refreshSuperUserGroupsConfiguration]
               [-refreshAdminAcls] 
               [-refreshServiceAcl]
               [-getGroups [username]]
               [-transitionToActive [--forceactive] [--forcemanual] <serviceId>]
               [-transitionToStandby [--forcemanual] <serviceId>]
               [-failover [--forcefence] [--forceactive] <serviceId1> <serviceId2>]
               [-getServiceState <serviceId>]
               [-checkHealth <serviceId>]
               [-help [cmd]]
               
              

hadoop jar /usr/hdp/current/hadoop-mapreduce-client/hadoop-mapreduce-examples.jar pi -Dmapred.job.queue.name=demo 10 100

https://github.com/hortonworks/simple-yarn-app
