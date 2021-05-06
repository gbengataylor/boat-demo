
04 doesn't kick off build after applying
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
      [{"from":{"kind":"ImageStreamTag","name":"boat-identify:latest","namespace":"boats-demo"},"fieldPath":"spec.template.spec.containers[?(@.name=="boat-identify")].image","pause":"false"}]   
```


07
```yaml
    image.openshift.io/triggers: >-
      [{"from":{"kind":"ImageStreamTag","name":"boat-group:latest","namespace":"boats-demo"},"fieldPath":"spec.template.spec.containers[?(@.name=="boat-group")].image","pause":"false"}]   
```
