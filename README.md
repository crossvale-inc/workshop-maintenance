# Workshop-Maintenance

## Workshop startup
To start the cluster in AWS N Virginia, startup the instances in the following order:
* infranode
* master
* nfs
* node 01,02,03,...(all numbered nodes)

**NOTE**: The cluster https://master.xv33.acumena-os.com must be on completely on before running the scripts

## Startup script
The services deploying within the OCP cluster as infrastructure for running the Workshop have to be started in a particular order.
Startup script will start them in the right order.

**NOTE**: After all pods come online, you will probably want to scale labs up depending on the number of attendees (3 replicas for around 25 poeple work great)

## During the workshop
To register attendees for the workshop add them (with the cluster on)onto 
http://etherpad-workshop-infra.cloudapps.xv33.acumena-os.com/p/roadshow

**NOTE**: Always leave user00 alone. Only perform cleanup users 01 to 99

## Checkup script
Checkup will search through users and tell you if the cluster is clean
       Line 3  "for i in `seq -w 00 99`;" determines the users to run through

## Cleanup script
Cleanup will delete and recreate each user
       Line 3  " range="01 99" "  determines the users to run through (***DO NOT INCLUDE USER 00****)

## Progress script
Progress is ran during the workshop to track progress of each user during the worshop

## Webhook script
Webhooks will find any webhooks that have been created and at this time they will need to be manually removed

## Shutdown script
The services deploying within the OCP cluster as infrastructure for running the Workshop have to be shutdown in a particular order.
Shutdown script will stop them in the right order.

Make sure to stop all instances when workshop is not being used.
