# Packer Prometheus with Ansible (Remote)

## System prepare

On you local machine you need to install
  * [packer](https://www.packer.io/intro/getting-started/install.html)
  * [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Available environment variables:

  * *aws_profile*: your AWS profile name
  * *aws_region*: your prefered AWS region
  * *prometheus_version*: prometheus version

## Building AWS AMI

Encrypted External Block Storage with termination protection will be used for storing persistent data.

    $ packer validate prometheus.json
    $ packer inspect prometheus.json
    $ packer build prometheus.json

You need to open *Inbound Custom TCP rule* *Port Range 9090* in your EC2 security group.

Prometheus will now be reachable at http://your_aws_ebs_public_dns:9090/.

