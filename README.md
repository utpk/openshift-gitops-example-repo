# openshift-gitops-example-repo
Example repository for GitOps and CI/CD with ArgoCD &amp; OpenShift GitOps Operator

#### application.yaml
```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: manage-access-example
spec:
  destination:
    namespace: mynamespace
    server: https://kubernetes.default.svc
  source:
    path: manage-access-example
    repoURL: https://github.com/utpk/openshift-gitops-example-repo.git
    targetRevision: main
    directory:
      recurse: true
  project: default
  syncPolicy:
    automated:
      prune: false
      selfHeal: false
```
