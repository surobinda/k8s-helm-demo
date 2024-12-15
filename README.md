# This is just a sample application to demonstrate Docker, k8s and helm chart

### Following are pre-requisite assuming one is tying the same in Windows platform 
* install docker desktop: https://docs.docker.com/desktop/setup/install/windows-install/
* install mini kube: https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download
* install scoop: https://www.makeuseof.com/windows-install-scoop/
    * in power shell run the command: iwr -useb get.scoop.sh | iex
* install open lens: https://github.com/MuhammedKalkan/OpenLens
    * scoop bucket add extras
    * scoop install openlens
* Note: openlens is a GUI tool to monitor k8s cluster and related objects 
* install helm: https://helm.sh/docs/intro/install/
    *  scoop install helm
### Next build the sample springboot application, build an docker image, publish image and deploy using helm
* mvn clean install
* command> docker build -t demo-app .
* command> docker run -d -p 8080:8080 --name demo-container demo-app
* command> docker image ls
* command> docker push demo-app surobinda/k8s-hands-on:demo-app
* command> helm install demo-app demo-app
* command> helm list
* command> kubectl get deployments
* command> kubectl get service

# I referred [Complete Helm Chart Tutorial: From Beginner to Expert Guide](https://www.youtube.com/watch?v=DQk8HOVlumI&t=80s)




