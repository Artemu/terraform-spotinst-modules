# spotinst_ocean_controller

This module will install the [Spotinst Kubernetes Controller][controller-api-url] for use when importing and managing clusters using Elastigroups with Spotinst Ocean. More information can be found in the offical [Spotinst Kubernetes Documentation][spotinst-k8s-api-url]

This module manages the following resources:
* kubernetes provider
	* kubernetes_config_map
	* kubernetes_secret
	* kubernetes_service_account
	* kubernetes_cluster_role
	* kubernetes_cluster_role_binding
	* kubernetes_deployment

## Variables
* host
* username
* password
* spotinst_account
* spotinst_token
* spotinst_cluster_identifier

## Example Use
Fill in the following arguments in example.tf:
```
module "spotinst_ocean_controller" {
  source = "git::git@github.com:spotinst/terraform-modules.git//spotinst_ocean_controller/?ref=v0.1.0"

  config_context_cluster = ""

  # host = ""
  # username = ""
  # password = ""

  spotinst_account = ""
  spotinst_token = ""
  spotinst_cluster_identifier = ""
}
```

We currently support authentication through either static host/username/password or through use of kubeconfig. Please update the template with your preferred method.

From within ./example, run the following commands:
```
terraform get
terrafomr apply
```

You will see "Apply complete!" if your plan is applied successfully.


[controller-api-url]: https://api.spotinst.com/container-management/kubernetes/kubernetes-tutorials/spotinst-kubernetes-controller/
[spotinst-k8s-api-url]: https://api.spotinst.com/container-management/kubernetes/