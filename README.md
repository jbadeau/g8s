# g8s
Kubernetes quality gates

```yaml
apiVersion: g8s.io/v1alpha1
kind: Test
metadata:
  name: todo-tests
  description: TODO tests
  labels:
    g8s.io/tags: regression
  annotations:
    g8s.io/jira-projext:
spec:
  type: bdd
  owner: todo-team
  system: todo
  definition:
    background:
      - list is empty
    scenario: create todo
      step: buy cucumber
    
    scenario: edit todo
      step: buy 2 cucumbers
```
