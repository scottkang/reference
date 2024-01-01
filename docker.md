# Container to image
Use docker commit option to create my image from a container.
```bash
$>docker commit -a "mint-mysql" mysql mint-repo:latest
```
* -a : author ex) scott.kang@gmail.com
* mysql : container name or id
* mint-repo : repository, image name
* latest : tag

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
