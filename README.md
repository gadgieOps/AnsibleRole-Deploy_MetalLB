# Ansible Role: Deploy metallb

Deploys metallb on a kubernetes control plane node. Based on installation documentation as per: [MetalLB Installation](https://metallb.universe.tf/installation/)

## Role Variables

~~~bash
version: "0.14.9"
~~~

Version of metallb to deploy

~~~bash
strict_arp: true
~~~

Set if strict_arp is enabled in kube-proxy when using ipvs.

~~~bash
remove: false
~~~

Will remove metallb rather than deploy it when set to true

## Example Playbook

~~~yaml
- name: Deploy metallb
  hosts: control-plane-node
  become: true
  roles:
  - role: gadgieOps.metallb
~~~

## License

MIT

## Author Information

Authored by gadgieOps
