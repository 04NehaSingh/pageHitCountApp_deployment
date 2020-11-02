# pageHitCountApp_deployment-

1. Start deployment using 

       kubectl apply -f .

2. Test the app using 
	
       http://nodeapp-svc.n1.svc.cluster.local:30007

3. Test load and Hpa by running 

       kubectl run -i --tty load-generator --image=11nehas/node-app /bin/sh -n n1
  then: 
        
	while true; do wget -q -O- http://nodeapp-svc.n1.svc.cluster.local:8081; done 

	once completed exit from container and delete load-generator under namespace n1


