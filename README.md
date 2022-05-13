
# g8s
Kubernetes native  contract  testing framework

```yaml
apiVersion: g8s.io/v1alpha1
kind: Test
metadata:
  name: create-todo
  title: Create TODO
  description: Create a new TODO.
  labels:
    g8s.io/flow: 1000000000000
    g8s.io/parentInteractionId: 2000000000000
    g8s.io/interactionId: 3000000000000
  annotations:
    g8s.io/consumer: todo-web
    g8s.io/provider: todo-service
spec:
  type: contract
  owner: todo-team
  system: todo
  definition:
	type: Synchronous/HTTP
	request:
	  method: GET
	  path: "/api/test/8"
	  matchingRules:
	    path:
	      matchers:
	      - match: regex
	        regex: "/api/test/\\d{1,8}"
	response:
	  status: 200
	  headers:
	    Content-Type: application/json
	  body:
	    contentType: application/json
	    encoded: false
	    content:
	    - size: 1445211
	      name: testId254
	      id: 32432
	  matchingRules:
	    body:
	      "$":
	        matchers:
	        - match: type
	          min: 1

```
