# ** COMMANDS USED DURING THE ASSIGNMENTS ** - 
	cd $home  ->to reach the root directory
	yum install git -y ->to install git or update
	git clone  https://github.com/ashishrpandey/example-voting-app -> cloning the example-voting-app application from git
	cd voting-app -> to get inside the example-voting-app
	ll -> list down the file and folder
	cd k8s-specifications -> to get inside the k8s-specifications directory
	kubectl apply -f . -> to create all the pods,services, deployments,replica-sets
	kubectl get all -> give all the information of pods, services, deployments amd replica-sets
	kubectls delete po <pod_name> -> it will delete the pod 
	kubectl logs <pod_name> - it will store all the activity logs.
	

# ** OBSERVATION OF DELETE VOTE POD ** -
	1.kubectl delete po <vote_pod_name> it will delete the pod 
	2.forentend observation -> nothing changed in frontend, we are able to vote properly, also we are able to see the voting result as well.
	3.one thing observed in voting page is the container ID is changed in voting page.
	4.in Unix also nothing changed, only a new pod is started after the delettation of the old pods
	5.also , we can only able to see the logs in new pod i.e. started.

# ** OBSERVATION OF DELETE WORKER POD ** -
	1.kubectl delete po <worker_pod_name> it will delete the pod
	2.after deleting worker node also noting changed in frontend as well as in unix. 
	3.as we deleted the worker node, a new worker node started and it starts giving the information by fetching from the DB.

# ** OBSERVATION OF DB POD ** -
	1.kubectl delete po <db_pod_name> it will delete the pod
	2.after deleting db we can observe that in result page we are unable to see any vote, because all db information is deleted.
	3.As pod deleted a new db pod started , which has empty data in the db.

# **WHY result app STOPPED working after db pod stop** - 
	1. result app stopped after db pod stop because , it lost connection with Db , so it unable to fetch the query of result. 
	2. So to start again we have to restart the result app. 

# **HOW YOU MADE THE RESULT POD work**
	by restart the result pod, so it will try to establish fresh connection with DB.
	And restart is happening because int the code , a error habdling is wtitten , for restart the pod. 
	
# **Learning**
	docker concepts amd commands
	Microservices architecture 
	kubernets concepts
		architecture
		contrillers
		services
		jobs
		delpoyment
	kubernets commands
	praticle observation by example-voting-app
