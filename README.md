# Run containers and virtual machines side-by-side with OpenShift Virtualization!

Kubernetes can run containers and traditional virtual machines side-by-side, and OpenShift with OpenShift Virtualization makes it easy. Best of all, you can run it all on a single bare-metal host! Please see my previous instructions for [getting started with Single Node OpenShift](https://github.com/ryannix123/single-node-openshift/blob/main/SNOing.md). 

My recommendation for hardware:

 1. Bare-metal host with 48 GBs of RAM
 2. Two hard drives. Preferrably NVME drives.
 3. At least 10 vCPUs

# CLI Tools

You'll want to download the latest version of the OpenShift CLI tool, `oc` which includes `kubectl` You can download the latest version for your specific OS from [here](https://mirror.openshift.com/pub/openshift-v4/x86_64/clients/ocp/stable/). I would highly recommend using a package manager like Homebrew to install them and keep them up-to-date. Additionally, you'll want to install Let's Encrypt so that you can use the `certbot` cli to request a certificate for your domain name.

You'll also want to create an OpenShift user without admin privileges. I find that generating an `htpasswd` user is easy to do. I've also [included instructions for that](https://github.com/ryannix123/single-node-openshift/blob/main/SNOing.md#add-a-non-admin-account-to-your-openshift-system) in my other repo.

## DNS

You'll want some kind of DNS name for your cluster. I use Cloudflare to manage my openshifthelp.com domain name. Instructins for creating the DNS entries can be found [here](https://github.com/ryannix123/single-node-openshift/blob/main/SNOing.md#add-three-dns-entries-to-get-started).

## Setting up the network

You'll want to use a DHCP reservation on your router. Make sure ports 443 and 6443 are open to your Single Node OpenShift's IP.

## Patching the cluster to use local storage
The instructions are in the video, and I have a storage folder that contains the commands you'll run to patch the container storage to use the [LVM Storage.](https://docs.openshift.com/container-platform/4.15/storage/persistent_storage/persistent_storage_local/persistent-storage-using-lvms.html)
