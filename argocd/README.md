docker build -t localhost:5000/argocd_ansible:latest .

docker push localhost:5000/argocd_ansible:latest

kubectl apply -n argocd -f install.yaml

disable auth: 
kubectl patch deploy argocd-server -n argocd -p '[{"op": "add", "path": "/spec/template/spec/containers/0/command/-", "value": "--disable-auth"}]' --type json

port forard:

kubectl port-forward svc/argocd-server -n argocd 8080:443



- Remove
kubectl delete -n argocd -f install.yaml