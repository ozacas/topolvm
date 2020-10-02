
This playbook performs a provision of topolvm on Arch Linux distributions 
(tested with Manjaro 20.06 on arm64 eg. RPI4) in the spirit of the deploy/README.md

What this play can do:
---------------------

Self-signed certificates are provisioned. Adaptation to other distributions should
be possible but it will require editing to handle differences between linux distros.

System Requirements
-------------------
Ansible 2.9 or later
Arch Linux kubernetes nodes (eg. Manjaro 20.06 or later)
kubectl
kustomize 3.8 (will be installed if not present)

Installation
------------

1) Setup certificates using a procedure similar to eg. 
   https://www.funkypenguin.co.nz/note/self-signed-certificate-on-mutating-webhook-requires-double-encryption/

2) Setup hosts.ini with nodes and ssh user for ansible to deploy topolvm

3) Edit group_vars/all as required

4) ansible-playbook -i hosts.ini -K install.yml

5) kubectl get pods -n topolvm-system
