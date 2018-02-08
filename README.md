# Workshop-Maintenance

# Scripts written by Ian Purdy for Maintenance and cleanup of workshops.
#
# 4 scripts: checkup, cleanup, progress, webhooks
#
# Cluster must be completely up (all nodes, or at least all nodes that have pods scheduled on them) before running the scripts
# To start the cluster in AWS N Virginia, startup
#   infranode
#   master
#   nfs
#   node 01,02,03,...all numbered nodes
#
#
# ***NOTE***
# Always leave user00 alone
# Only perform cleanup users 01 to 99
#
#
# Checkup will search through users and tell you if the cluster is clean
#        Line 3  "for i in `seq -w 00 99`;" determines the users to run through
#
# Cleanup will delete all existing projects (except core ones like default, workshop-infra, etc.) and recreate each project required for the workshop
#        Line 3  " range="01 99" "  determines the users to run through (***DO NOT INCLUDE USER 00****)
#
# Progress is run during the workshop to track progress of each user during the worshop
#
# Webhooks will find any webhooks that have been created and at this time they will need to be manually removed. It will also identify all 
# 1.2.0/src/main/java/com/openshift/evg/roadshow/parks/rest/BackendController.java files that have been changed. These will need to be 
# restored to their original state manually too.
#
#
# To register attendees for the workshop add them (with the cluster up) to 
#  http://etherpad-workshop-infra.cloudapps.xv33.acumena-os.com/p/roadshow
#
#
# Make sure to stop all instances when workshop is not being used.
