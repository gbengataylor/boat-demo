
04 doesn't kick off build after applying but 03 does...is it because it is s2i from source vs docker strategy
may need oc start-build s2i-ubi8-py38-opengl

05- 
add annotations
```yaml
    image.openshift.io/triggers: >-
      [{"from":{"kind":"ImageStreamTag","name":"boat-detect:latest","namespace":"boats-demo"},"fieldPath":"spec.template.spec.containers[?(@.name==\"boat-detect\")].image","pause":"false"}]
```

06
```yaml
    image.openshift.io/triggers: >-
      [{"from":{"kind":"ImageStreamTag","name":"boat-identify:latest","namespace":"boats-demo"},"fieldPath":"spec.template.spec.containers[?(@.name==\"boat-identify\")].image","pause":"false"}]   
```


07
```yaml
    image.openshift.io/triggers: >-
      [{"from":{"kind":"ImageStreamTag","name":"boat-group:latest","namespace":"boats-demo"},"fieldPath":"spec.template.spec.containers[?(@.name==\"boat-group\")].image","pause":"false"}]   
      
```
08

does the username actually matter since you're telling it to preload the git repo when the notebook is selected
(can't mix '_' with '-")

is the point to have a default profile per user? or one for all? yes it's per user..how can we make a default profile for all?


TODO
remove hardcoded things like namespace
use env vars
ansible?

Notebook


running first notebook
had to install app package
file path is wrong

