# Laravel K8s

## Restart Resource
```
kubectl rollout restart deployment/laravel-deployment
```

## Configmap
##### Create ConfigMaps from files
```
kubectl create configmap laravel-configmap --from-file=config/nginx.conf
```

##### Update ConfigMaps
```
kubectl create configmap laravel-configmap --from-file=config/nginx.conf -o yaml --dry-run | kubectl replace -f -
```

## Secret
##### Create Secret from env file
```
kubectl create secret generic laravel-secret --from-env-file=config/env-example
```

##### Update Secret
```
kubectl create secret generic laravel-secret --from-env-file=config/env-example --dry-run -o yaml | kubectl apply -f -
```

##### Encode Secret Before Set Secret in yaml
```
echo -n ‘hello’ | base64
```

##### Decode Secret
```
echo -n ‘glhs4=’ | base64 —decode
```
