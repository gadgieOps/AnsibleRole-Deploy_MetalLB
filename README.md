# Ansible Role: Deploy metallb

Deploys MetalLB on a Kubernetes Cluster. Based on installation documentation as per: [MetalLB Installation](https://metallb.universe.tf/installation/)

## Installation

```bash
ansible-galaxy install git+https://github.com/gadgieOps/AnsibleRole-Deploy_MetalLB.git
```

## Role Variables

```yaml
version: "0.14.9"
```

Version of MetalLB to deploy.

```yaml
manifest_url: https://raw.githubusercontent.com/metallb/metallb/v{{ version }}/config/manifests/metallb-native.yaml
```

URL of the MetalLB manifest to deploy.

```yaml
install_method: kubectl
```

Installation method. Options are:

- `kubectl-cmd`: Uses the `kubectl` CLI.
- `kubectl`: Uses the `kubernetes.core` Ansible modules.

```yaml
state: present
```

State of the MetalLB deployment. Options are `present` (deploy) or `absent` (remove).

```yaml
kubeconfig_path: "{{ ansible_env.HOME }}/.kube/config"
```

Path to the Kubernetes kubeconfig file.

```yaml
download_manifest: false
```

Whether to download the MetalLB manifest locally.

```yaml
manifest_dir: "{{ ansible_env.HOME }}/.kubernetes-manifests/metallb"
```

Directory to store the downloaded manifest.

```yaml
manifest_dir_owner: "{{ ansible_env.USER }}"
manifest_dir_group: "{{ ansible_env.USER }}"
```

Owner and group of the manifest directory.

```yaml
manifest: metallb.yml
```

Name of the manifest file.

```yaml
manifest_owner: "{{ ansible_env.USER }}"
manifest_group: "{{ ansible_env.USER }}"
```

Owner and group of the manifest file.

```yaml
strict_arp: true
```

Set if strict ARP is enabled in kube-proxy when using IPVS.

## Example Playbook

```yaml
- name: Deploy metallb
  hosts: localhost
  become: false
  roles:
  - role: gadgieOps.metallb
```

## License

MIT

## Author Information

Authored by gadgieOps
