apiVersion: v1
kind: Service
metadata:
  name: web
  labels:
    service: web
spec:
  type: LoadBalancer
  ports:
  - port: 80
    targetPort: 3333
  selector:
    web: rails

---

apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: d-web
spec:
  replicas: 7
  template:
    metadata:
      labels:
        web: rails
    spec:
      containers:
      - name: web
        image: radhikakancharla/popcorn:$BUILD_NUMBER
        ports:
        - containerPort: 3333