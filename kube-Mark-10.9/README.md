# App deployment to cluster using digital.ai deployment

Test version of the digital ai (XL Deploy) can be installed using the below docker command.

      docker run -e ADMIN_PASSWORD=admin -e ACCEPT_EULA=Y -d --network host  -p 4516:4516 -v /home/sai/my-kubeconfig.yaml:/opt/xl-deploy/kubeconfig.yaml --name xl-deploy  xebialabs/xl-deploy:25.3

- network host ---> used to connect to the local device so it can access the local cluster hosted in PC.

### Connecting the infrastrecture
- To connect the cluster, we need to configure the infrastecture part in the XL deploy. First we need to check the minikube configuration with the help of below commands

              kubectl config view  ---> for getting the ca.cert,client.crt,client.keys paths and the api link of minikube
              cat ~/.minikube/ca.crt |base64 -w 0
              cat ~/.minikube/profiles/minikube/client.crt |base64 -w 0
              cat ~/.minikube/profiles/minikube/client.key |base64 -w 0
- we need to encode the cert , ca, key in the base64.
- wew can test the connect and see if the XL Deploy can access the minilube external.
