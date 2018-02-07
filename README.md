# Workshop-Maintenance

# Scripts written by Ian Purdy for Maintenance and cleanup of workshops.
#
# 4 scripts: checkup, cleanup, progress, webhooks
#
# Cluster must be on completely on before running the scripts
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
# Cleanup will delete and recreate each user
#        Line 3  " range="01 99" "  determines the users to run through (***DO NOT INCLUDE USER 00****)
#
# Progress is ran during the workshop to track progress of each user during the worshop
#
# Webhooks will find any webhooks that have been created and at this time they will need to be manually removed
#
#
# To register attendees for the workshop add them (with the cluster on)onto 
#  http://etherpad-workshop-infra.cloudapps.xv33.acumena-os.com/p/roadshow
