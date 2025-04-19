# Ansible Role: Deploy metallb

Deploys MetalLB on a Kubernetes Cluster. Based on installation documentation as per: [MetalLB Installation](https://metallb.universe.tf/installation/)

## Installation

```bash
ansible-galaxy install git+https://github.com/gadgieOps/AnsibleRole-Deploy_MetalLB.git
```

## Role Variables

```bash
version: "0.14.9"
```

Version of MetalLB to deploy

```bash
strict_arp: true
```

Set if strict_arp is enabled in kube-proxy when using ipvs.

```bash
remove: false
```

Will remove MetalLB rather than deploy it when set to true

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
