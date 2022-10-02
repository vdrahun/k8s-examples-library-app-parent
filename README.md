argocd app create library \
--dest-namespace argocd \
--dest-server https://kubernetes.default.svc \
--repo https://github.com/vdrahun/k8s-examples-library-app-parent.git \
--path k8s/argocd

argocd app sync apps