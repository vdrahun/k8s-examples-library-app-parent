brew install argocd

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

argocd login --port-forward

argocd app create library \
--dest-namespace argocd \
--dest-server https://kubernetes.default.svc \
--repo https://github.com/vdrahun/k8s-examples-library-app-parent.git \
--path k8s/argocd

argocd app sync library