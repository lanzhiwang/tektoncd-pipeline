# pipeline

```bash
$ kubectl apply -f pipeline/previous/v0.57.0/release.yml

namespace
	tekton-pipelines
	tekton-pipelines-resolvers

clusterrole.rbac.authorization.k8s.io
	tekton-pipelines-controller-cluster-access
	tekton-pipelines-controller-tenant-access
	tekton-pipelines-webhook-cluster-access
	tekton-events-controller-cluster-access
	tekton-aggregate-edit
	tekton-aggregate-view
	tekton-pipelines-resolvers-resolution-request-updates

role.rbac.authorization.k8s.io
	tekton-pipelines-controller
	tekton-pipelines-webhook
	tekton-pipelines-events-controller
	tekton-pipelines-leader-election
	tekton-pipelines-info
	tekton-pipelines-resolvers-namespace-rbac

serviceaccount
	tekton-pipelines-controller
	tekton-pipelines-webhook
	tekton-events-controller
	tekton-pipelines-resolvers

clusterrolebinding.rbac.authorization.k8s.io
	tekton-pipelines-controller-cluster-access
	tekton-pipelines-controller-tenant-access
	tekton-pipelines-webhook-cluster-access
	tekton-events-controller-cluster-access
	tekton-pipelines-resolvers

rolebinding.rbac.authorization.k8s.io
	tekton-pipelines-controller
	tekton-pipelines-webhook
	tekton-pipelines-controller-leaderelection
	tekton-pipelines-webhook-leaderelection
	tekton-pipelines-info
	tekton-pipelines-events-controller
	tekton-events-controller-leaderelection
	tekton-pipelines-resolvers-namespace-rbac

customresourcedefinition.apiextensions.k8s.io
	clustertasks.tekton.dev
	customruns.tekton.dev
	pipelines.tekton.dev
	pipelineruns.tekton.dev
	resolutionrequests.resolution.tekton.dev
	stepactions.tekton.dev
	tasks.tekton.dev
	taskruns.tekton.dev
	verificationpolicies.tekton.dev

secret
	webhook-certs

validatingwebhookconfiguration.admissionregistration.k8s.io
	validation.webhook.pipeline.tekton.dev
	config.webhook.pipeline.tekton.dev

mutatingwebhookconfiguration.admissionregistration.k8s.io
	webhook.pipeline.tekton.dev

configmap
	config-defaults
	config-events
	feature-flags
	pipelines-info
	config-leader-election-controller
	config-leader-election-events
	config-leader-election-webhook
	config-logging
	config-observability
	config-registry-cert
	config-spire
	config-tracing
	bundleresolver-config
	cluster-resolver-config
	resolvers-feature-flags
	config-leader-election-resolvers
	config-logging
	config-observability
	git-resolver-config
	http-resolver-config
	hubresolver-config

deployment.apps
	tekton-pipelines-controller
	tekton-pipelines-remote-resolvers
	tekton-pipelines-webhook
	tekton-events-controller

service
	tekton-pipelines-controller
	tekton-events-controller
	tekton-pipelines-remote-resolvers
	tekton-pipelines-webhook

horizontalpodautoscaler.autoscaling
	tekton-pipelines-webhook

```

# triggers

```bash
$ kubectl apply -f triggers/previous/v0.26.1/release.yml

clusterrole.rbac.authorization.k8s.io
	tekton-triggers-admin
	tekton-triggers-core-interceptors
	tekton-triggers-core-interceptors-secrets
	tekton-triggers-eventlistener-roles
	tekton-triggers-eventlistener-clusterroles
	tekton-triggers-aggregate-edit
	tekton-triggers-aggregate-view

role.rbac.authorization.k8s.io
	tekton-triggers-admin-webhook
	tekton-triggers-core-interceptors
	tekton-triggers-info

serviceaccount
	tekton-triggers-controller
	tekton-triggers-webhook
	tekton-triggers-core-interceptors

clusterrolebinding.rbac.authorization.k8s.io
	tekton-triggers-controller-admin
	tekton-triggers-webhook-admin
	tekton-triggers-core-interceptors
	tekton-triggers-core-interceptors-secrets

rolebinding.rbac.authorization.k8s.io
	tekton-triggers-webhook-admin
	tekton-triggers-core-interceptors
	tekton-triggers-info

customresourcedefinition.apiextensions.k8s.io
	clusterinterceptors.triggers.tekton.dev
	clustertriggerbindings.triggers.tekton.dev
	eventlisteners.triggers.tekton.dev
	interceptors.triggers.tekton.dev
	triggers.triggers.tekton.dev
	triggerbindings.triggers.tekton.dev
	triggertemplates.triggers.tekton.dev

secret
	triggers-webhook-certs

validatingwebhookconfiguration.admissionregistration.k8s.io
	validation.webhook.triggers.tekton.dev
	config.webhook.triggers.tekton.dev

mutatingwebhookconfiguration.admissionregistration.k8s.io
	webhook.triggers.tekton.dev


configmap
	config-defaults-triggers
	feature-flags-triggers
	triggers-info
	config-leader-election-triggers-controller
	config-leader-election-triggers-webhook
	config-logging-triggers
	config-observability-triggers

service
	tekton-triggers-controller
	tekton-triggers-webhook

deployment.apps
	tekton-triggers-controller
	tekton-triggers-webhook



$ kubectl apply -f triggers/previous/v0.26.1/interceptors.yml

secret
	tekton-triggers-core-interceptors-certs

deployment.apps
	tekton-triggers-core-interceptors

service
	tekton-triggers-core-interceptors

clusterinterceptor.triggers.tekton.dev
	cel
	bitbucket
	slack
	github
	gitlab

```




# chains

```bash
$ kubectl apply -f chains/previous/v0.20.1/release.yml

namespace
	tekton-chains

secret
	signing-secrets

configmap
	chains-config
	chains-info
	tekton-chains-config-leader-election
	config-logging
	tekton-chains-config-observability

deployment.apps
	tekton-chains-controller

clusterrolebinding.rbac.authorization.k8s.io
	tekton-chains-controller-cluster-access
	tekton-chains-controller-tenant-access

clusterrole.rbac.authorization.k8s.io
	tekton-chains-controller-cluster-access
	tekton-chains-controller-tenant-access

serviceaccount
	tekton-chains-controller

role.rbac.authorization.k8s.io
	tekton-chains-leader-election
	tekton-chains-info

rolebinding.rbac.authorization.k8s.io
	tekton-chains-controller-leaderelection
	tekton-chains-info

service
	tekton-chains-metrics

```
