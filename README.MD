# HAProxy & Nginx

Application consist of 2 nginx instances and a single HAProxy instance which
spread HTTP traffic between them.
```
                  (HTTPS)
                ┌─────────┐
                │ HAProxy │
                └────┬────┘
                     │
   ┌─────────┐(HTTP) │ (HTTP)┌─────────┐
   │  Nginx  │◄──────┴──────►│  Nginx  │
   └─────────┘               └─────────┘
```


Repository contains all necessary files to start all services.  
In order to start application, execute following command in main directory.
```
docker compose up
```

---
**Notice!**  
This is not a good practice to keep files like certificates in repository.
Certificate file `./selfsigned.pem` has been added just for easier start
purposes, do not use this certificate in production environment.
