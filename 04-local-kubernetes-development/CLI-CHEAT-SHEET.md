# CLI-CHEAT-SHEET

## start talk
``` bash
cd ~/src/github.com/pandorasnox/presentations/04-local-kubernetes-development

make start-talk

```

## demo app intro

``` bash
cd ~/src/github.com/pandorasnox/kubestagram/

code .

# explain struct

# start kubestaback + curl
cd ~/src/github.com/pandorasnox/kubestagram/kubestaback


# change env file cors = false

docker-compose up

# curl get
curl http://localhost:22080

# curl post image
cd ~/Downloads/example_img/ && curl -i -X POST -H "Content-Type: multipart/form-data" -F "imgdata=@example.jpg" http://localhost:22080

# curl get
curl http://localhost:22080


############################## start kubestafront



```

