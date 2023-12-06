 - helm upgrade --install cert-manager jetstack/cert-manager -n cert-manager -f cert.yaml --create-namespace
 - helm upgrade --install ingress-nginx ingress-nginx --repo https://kubernetes.github.io/ingress-nginx -n ingress-nginx --create-namespace
 - helm upgrade --install prometheus prometheus-community/prometheus -f prometheus.yaml -n monitoring --create-namespace

 - kubectl create secret generic keycloak-truststore -n keycloak --from-file=keycloak.truststore.jks=./keycloak.truststore.jks
 - helm upgrade --install keycloak codecentric/keycloak -n keycloak -f keycloak.yaml --create-namespace
 - helm upgrade --install harbor harbor/harbor -n harbor -f harbor.yaml --create-namespace
