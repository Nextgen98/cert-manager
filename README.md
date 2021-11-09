# cert-manager

# Installation 
  - kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.6.0/cert-manager.yaml
# Create namespace certmangaer
   -  kubectl create ns cert-manager
# Hookup cert-manager with lets Encrypt
 -  kubectl apply -f issuer.yaml
#  Deploy Certificate 
- kubectl apply -f certificate.yaml

  