# Laravel K8s

## Configmap
##### Create ConfigMaps from files
```
kubectl create configmap laravel-configmap --from-file=config/nginx.conf
```

## Secret
##### Create Secret from env file
```
kubectl create secret generic laravel-secret --from-env-file=.test-secret
```

##### Update Secret
```
kubectl create secret generic laravel-secret --from-env-file=env-example --dry-run -o yaml | kubectl apply -f -
```

##### Encode Secret
```
echo -n ‘hello’ | base64
```

##### Decode Secret
```
echo -n ‘glhs4=’ | base64 —decode
```
