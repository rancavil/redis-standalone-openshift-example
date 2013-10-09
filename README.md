Redis on Openshift
==================

This helps you to install and run Redis.io on Openshift.

Create an application on Openshift. For example an nodejs application.

     $ rhc app create MyNodeApp nodejs-0.6

Go to the app directory.

     $ cd MyNodeApp
     $ git remote add upstream -m master git://github.com/rancavil/redis-standalone-openshift-example.git
     $ git pull -s recursive -X theirs upstream master

Push the repo upstream.

     $ git push

Then redis.io will be build on Openshift.

You can verify the installation using SSH to connect with the Openshift user account, and  execute.

     $ cd app-root/repo/bin
     $ ./redis-cli -h $OPENSHIFT_NODEJS_IP -p 16000 ping
     PONG

Other example.

     $ ./redis-cli -h $OPENSHIFT_NODEJS_IP -p 16000
     redis 127.7.232.129:16000> set mykey "rodrigo"
     OK
     redis 127.7.232.129:16000> get mykey
     "rodrigo"
     redis 127.7.232.129:16000> 


