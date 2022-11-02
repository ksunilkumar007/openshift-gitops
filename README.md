# openshift-gitops

oc project iap-cicd-pipelines

oc apply -f task.yaml

oc apply -f pipeline.yaml

oc apply -f TriggerBinding.yaml

oc apply -f TriggerTemplate.yaml

oc apply -f EventListener.yaml

oc apply -f pipeline-sa.yaml


oc label namespace iap-cicd-pipelines operator.tekton.dev/enable-annotation=enabled

Create a route for EventListener Service (apps & with public label)


# ArgoCD
oc project microservice-namespace

oc label namespace microservice-namespace argocd.argoproj.io/managed-by=openshift-gitops

oc project openshift-gitops

oc apply -f argocd-service-appointment.yaml
