# App deployment to cluster using digital.ai deployment

Test version of the digital ai (XL Deploy) can be installed using the below docker command.

      docker run \
      -e ADMIN_PASSWORD=admin \
      -e ACCEPT_EULA=Y \
      -p 4516:4516 \
      --name xl-deploy \
      xebialabs/xl-deploy:25.3
