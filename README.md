# How to create an Operator on OpenShift 4.5

This introduction contains the installation and configuration such as an example how to develop OpenShift-Operators using the
operator-sdk with Ansible.


## Install & Prepare the operator-sdk on Fedorra 32

Install GO:
```bash
~:$ sudo dnf -y update
~:$ sudo dnf -y install go
```

Install operator-sdk:

```bash
~:$ cd /usr/local/bin
/usr/local/bin:$ RELEASE_VERSION=v0.17.0
/usr/local/bin:$ sudo curl -OJL https://github.com/operator-framework/operator-sdk/releases/download/${RELEASE_VERSION}/operator-sdk-${RELEASE_VERSION}-x86_64-linux-gnu
/usr/local/bin:$ sudo chmod +x operator-sdk-${RELEASE_VERSION}-x86_64-linux-gnu
/usr/local/bin:$ sudo mv operator-sdk-v0.17.0-x86_64-linux-gnu operator-sdk
~:$ operator-sdk version
```


## Create Project

```bash
~:$ operator-sdk new workshop-operator \
--api-version=workshops.operator.redhatgov.io/v1 \
--kind=Workshop \
--type=ansible \
--cluster-scope
```
