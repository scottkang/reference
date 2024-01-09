# Container to image
Use docker commit option to create my image from a container.
```bash
$>docker commit -a "mint-mysql" mysql mint-repo:latest
```
* -a : author ex) scott.kang@gmail.com
* mysql : container name or id
* mint-repo : repository, image name
* latest : tag   
This command <i style="color:red">does not maintain the data generated after the container is started</i>.

# Image export
Use docker save option to make an image to .tar file.
```bash
$>docker save -o mint-mysql.tar mint-repo
```
* -o : output file 
* mint-repo : image name or id

# Image import
Use docker load option to import an tar file into local repository.
```bash
$>docker load -i mint-mysql.tar
```

* -i : input tar file

# Container to image with data 

Use docker cp command
```bash
docker cp 9a:/var/lib/mysql /tmp
```
9a : container id or name
/var/lib/mysql : source directory (container)
/tmp : target directory (host)   

If the source data may be updated while copying, stop the container and execute this command.

# Login to the container
```bash
$>docker exec -it d4 /bin/bash
```
* d4 : container id
* /bin/bash : command to execute
