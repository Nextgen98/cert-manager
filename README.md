# cert-manager

# Installation 
  - kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.6.0/cert-manager.yaml
# Create namespace certmangaer
   -  kubectl create ns cert-manager
# Hookup cert-manager with lets Encrypt
 -  kubectl apply -f issuer.yaml
#  Deploy Certificate 
- kubectl apply -f certificate.yaml

  
  
  apiVersion: v1
kind: Service
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"v1","kind":"Service","metadata":{"annotations":{},"labels":{"app":"istio-ingressgateway","install.operator.istio.io/owning-resource":"example-istiocontrolplane","install.operator.istio.io/owning-resource-namespace":"istio-system","istio":"ingressgateway","istio.io/rev":"default","operator.istio.io/component":"IngressGateways","operator.istio.io/managed":"Reconcile","operator.istio.io/version":"1.9.4","release":"istio"},"name":"istio-ingressgateway","namespace":"istio-system"},"spec":{"ports":[{"name":"status-port","port":15021,"protocol":"TCP","targetPort":15021},{"name":"http2","port":80,"protocol":"TCP","targetPort":80},{"name":"https","port":443,"protocol":"TCP","targetPort":8443},{"name":"tcp-istiod","port":15012,"protocol":"TCP","targetPort":15012},{"name":"tls","port":15443,"protocol":"TCP","targetPort":15443}],"selector":{"app":"istio-ingressgateway","istio":"ingressgateway"},"type":"LoadBalancer"}}
  creationTimestamp: "2021-06-15T11:18:19Z"
  labels:
    app: istio-ingressgateway
    install.operator.istio.io/owning-resource: example-istiocontrolplane
    install.operator.istio.io/owning-resource-namespace: istio-system
    istio: ingressgateway
    istio.io/rev: default
    operator.istio.io/component: IngressGateways
    operator.istio.io/managed: Reconcile
    operator.istio.io/version: 1.9.4
    release: istio
  managedFields:
  - apiVersion: v1
    fieldsType: FieldsV1
    fieldsV1:
      f:metadata:
        f:annotations:
          f:kubectl.kubernetes.io/last-applied-configuration: {}
        f:labels:
          f:app: {}
          f:install.operator.istio.io/owning-resource: {}
          f:install.operator.istio.io/owning-resource-namespace: {}
          f:istio: {}
          f:istio.io/rev: {}
          f:operator.istio.io/component: {}
          f:operator.istio.io/managed: {}
          f:operator.istio.io/version: {}
          f:release: {}
      f:spec:
        f:ports:
          k:{"port":80,"protocol":"TCP"}:
            .: {}
            f:name: {}
            f:port: {}
            f:protocol: {}
            f:targetPort: {}
          k:{"port":443,"protocol":"TCP"}:
            .: {}
            f:name: {}
            f:port: {}
            f:protocol: {}
            f:targetPort: {}
          k:{"port":15012,"protocol":"TCP"}:
            .: {}
            f:name: {}
            f:port: {}
            f:protocol: {}
            f:targetPort: {}
          k:{"port":15021,"protocol":"TCP"}:
            .: {}
            f:name: {}
            f:port: {}
            f:protocol: {}
            f:targetPort: {}
          k:{"port":15443,"protocol":"TCP"}:
            .: {}
            f:name: {}
            f:port: {}
            f:protocol: {}
            f:targetPort: {}
        f:selector:
          f:app: {}
          f:istio: {}
        f:type: {}
    manager: istio-operator
    operation: Apply
    time: "2021-07-22T11:45:50Z"
  name: istio-ingressgateway
  namespace: istio-system
  resourceVersion: "54502183"
  selfLink: /api/v1/namespaces/istio-system/services/istio-ingressgateway
  uid: 5d8c35d6-ed00-4852-a19c-46e1a432e8cc
spec:
  clusterIP: 10.244.17.157
  clusterIPs:
  - 10.244.17.157
  externalTrafficPolicy: Cluster
  ports:
  - name: status-port
    nodePort: 30669
    port: 15021
    protocol: TCP
    targetPort: 15021
  - name: http2
    nodePort: 32713
    port: 80
    protocol: TCP
    targetPort: 80
  - name: https
    nodePort: 32251
    port: 443
    protocol: TCP
    targetPort: 8443
  - name: tls
    nodePort: 31899
    port: 15443
    protocol: TCP
    targetPort: 15443
  - name: tcp-istiod
    nodePort: 31319
    port: 15012
    protocol: TCP
    targetPort: 15012
  selector:
    app: istio-ingressgateway
    istio: ingressgateway
  sessionAffinity: None
  type: LoadBalancer
status:
  loadBalancer: {}
