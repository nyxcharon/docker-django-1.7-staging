# docker-django-1.7-staging
Staging container with django 1.7, postgres, redis and celery.
Run it with  
```# docker run -ti --net=host nyxcharon/docker-django-1.7-staging```   
From here git clone your project or start a new one.  

Known issue:
--------------------------------------
If you get this message:  
  ```  
  # service postgresql start  
   Starting PostgreSQL 9.3 database server*   
   The PostgreSQL server failed to start. Please check the log output:  
  2015-05-01 19:04:36 UTC FATAL:  could not access private key file "/etc/ssl/private/ssl-cert-snakeoil.key":        Permission denied   [fail] '  
  ```

Delete the image: ```# docker rmi imageid```  
Edit /etc/default/docker.io , add  ```DOCKER_OPTS="--storage-driver=devicemapper"  ```  
Restart the service  ```# service docker.io restart  ```  
Re-run (and pull) the image:  ```# docker run -ti --net=host nyxcharon/docker-django-1.7-staging  ```  



