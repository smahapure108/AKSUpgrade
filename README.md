Trigger: The pipeline triggers on changes to the main branch.
Variables: Define variables for resource group, AKS cluster name, node pool name, Kubernetes version, namespace, application name, and Pod Disruption Budget name.
Stages:
UpgradeAKS: This stage includes jobs to upgrade the AKS control plane and the node pool.
UpgradeControlPlane: Upgrade the AKS control plane to the specified Kubernetes version.
UpgradeNodePool: Drain the nodes in the node pool, upgrade the node pool, and uncordon the nodes after the upgrade.
DeployApp: This stage deploys the application with a rolling update strategy and applies a Pod Disruption Budget.
Deploy: Apply the PDB, deploy the application, and monitor the resource usage.
