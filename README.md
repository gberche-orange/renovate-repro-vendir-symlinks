# renovate-repro-vendir-symlinks
A reproduction repo to vendir sync missing symlinked artefacts, tracked into https://github.com/carvel-dev/vendir/issues/57

```shell
vendir version
#> vendir version 0.42.0
#> 
#> Succeeded

cd submodules
vendir sync 
#> Fetching: cf-deployment + . (git from https://github.com/cloudfoundry/cf-deployment/@v26.7.0)
#>   --> git -c advice.detachedHead=false checkout v26.7.0
#>   HEAD is now at 224943d2 Update cf-deployment manifest version to v26.7.0
#>   --> git submodule update --init --recursive
#>   --> git rev-parse HEAD
#>   224943d2668b17eed5a955fd882954ee43cdc1f7
#>   --> git describe --tags 224943d2668b17eed5a955fd882954ee43cdc1f7
#>   v26.7.0
#>   --> git log -n 1 --pretty=%B 224943d2668b17eed5a955fd882954ee43cdc1f7
#>   Update cf-deployment manifest version to v26.7.0
#>   
#> 
#> vendir: Error: Unable to resolve symlink: lstat cf-deployment/operations/use-metric-store.yml: no such file or directory
```
