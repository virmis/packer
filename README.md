# Packer Prometheus

## System prepare

You need to install [packer](https://www.packer.io/intro/getting-started/install.html).

## Available environment variables:

  * *aws_profile*: your AWS profile name
  * *aws_region*: your prefered AWS region
  * *prometheus_version*: prometheus version

## Building AWS AMI

Encrypted External Block Storage with termination protection will be used for storing persistent data.

    $ packer build prometheus.json

After you launch you image, you need to open *Inbound Custom TCP rule* *Port Range 9090* in your security group.

Prometheus will now be reachable at http://your_aws_ebs_public_dns:9090/.

