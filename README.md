# Create a nginx AWS box ubuntu lts - README.md with instructions (gh repo)

## Intro
This manual is dedicated to create a nginx AWS box ubuntu lts. Tested on Mac OS X.

## Requirements

- Hashicorp packer recent version installed
[Packer installation manual](https://learn.hashicorp.com/tutorials/packer/getting-started-install)

- git installed
[Git installation manual](https://git-scm.com/download/mac)

- have Aws cli installed 
[Aws cli installation guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-mac.html)

## Preparation 
- Clone git repository. 

```bash
git clone https://github.com/antonakv/packer-aws-nginx64
```

Expected command output looks like this:

```bash
Cloning into 'packer-aws-nginx64'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 12 (delta 1), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (1/1), done.
```

- Change folder to packer-aws-nginx64

```bash
cd packer-aws-nginx64
```

## Build
- In the same folder you were before run 

```bash
packer build template.json
```

Sample result

```bash
➜  packer-aws-nginx64 git:(f-awsimage) ✗ packer build template.json
amazon-ebs: output will be in this color.

==> amazon-ebs: Prevalidating any provided VPC information
==> amazon-ebs: Prevalidating AMI Name: packer-aws-nginx64
    amazon-ebs: Found Image ID: ami-0e0102e3ff768559b
==> amazon-ebs: Creating temporary keypair: packer_60421a35-12d7-6068-3d18-fc7b76741052
==> amazon-ebs: Creating temporary security group for this instance: packer_60421a37-27a7-93f0-7372-11de4e2576f0
==> amazon-ebs: Authorizing access to port 22 from [0.0.0.0/0] in the temporary security groups...
==> amazon-ebs: Launching a source AWS instance...
==> amazon-ebs: Adding tags to source instance
    amazon-ebs: Adding tag: "Name": "Packer Builder"
    amazon-ebs: Instance ID: i-06d2f19fd26e463e6
==> amazon-ebs: Waiting for instance (i-06d2f19fd26e463e6) to become ready...
==> amazon-ebs: Using ssh communicator to connect: 35.157.241.239
==> amazon-ebs: Waiting for SSH to become available...
==> amazon-ebs: Connected to SSH!

[ Removed some lines]

==> amazon-ebs: Waiting for the instance to stop...
==> amazon-ebs: Creating AMI packer-aws-nginx64 from instance i-06d2f19fd26e463e6
    amazon-ebs: AMI: ami-091d856a5f5701931
==> amazon-ebs: Waiting for AMI to become ready...
==> amazon-ebs: Terminating the source AWS instance...
==> amazon-ebs: Cleaning up any extra volumes...
==> amazon-ebs: No volumes to clean up, skipping
==> amazon-ebs: Deleting temporary security group...
==> amazon-ebs: Deleting temporary keypair...
Build 'amazon-ebs' finished after 3 minutes 33 seconds.

==> Wait completed after 3 minutes 33 seconds

==> Builds finished. The artifacts of successful builds are:
--> amazon-ebs: AMIs were created:
eu-central-1: ami-091d856a5f5701931
```
