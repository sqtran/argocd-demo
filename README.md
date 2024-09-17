# argocd-demo

This is just a sample repository that contains applications to demonstrate how ArgoCD works.  There's also some Custom Metrics Autoscaler configuration in here that was added as part of another demo.


## Getting Started

- Make sure the OpenShift GitOps Operator is installed.  Using the default settings should be good enough for this demo.

- Log into ArgoCD.  If this is a fresh, default installation, you can grab the Admin credentials from the `Secret` named *openshift-gitops-cluster* in the `openshift-gitops` namespace.

    **NOTE** Do not confuse this with the other `Secrets` that also contain similar-looking admin credentials.


- Create an ArgoCD Application


    ### Example 1 - Configure the KEDA Operator from a specific folder in the repo

    * Set namespace to `openshift-keda`
    * Set repo to https://github.com/sqtran/argocd-demo
    * Set path to keda

    **NOTE** Sometimes the first deployment of the KEDA operator, and its dependencies get stuck.  If the sync fails, try deleting the openshift-keda namespace and let ArgoCD rebuild it again.


    ### Example 2 - Deploy sample apps from root folder

    * Set namespace to your own namespace
    * Set repo to https://github.com/sqtran/argocd-demo
    * Make sure recurse folder is turned off
