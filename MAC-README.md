# mac related stuff

- do composer update
composer update

docker run -it --rm -v $(pwd):/source composer bash -c 'cd /source && composer update'

## on mac
minikube mount $(pwd):/host-timescreemer
```
     volumes:
      - name: app-source
        hostPath:
          path: /host-timescreemer
          type: Directory
      - name: nginx-conf
        hostPath:
          path: /host-timescreemer/kubernetes/container/httpserver/nginx/conf
          type: Directory
```

# other
- before: generate nginx.conf (ci/cd, ansible, whatever)
    - `kubectl create secret generic nginx --from-file nginx.conf`
