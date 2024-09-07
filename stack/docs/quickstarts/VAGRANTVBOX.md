# Quick start guide for Vagrant and VirtualBox

This option will create the stack in a Virtualbox VM using Vagrant.
This option will also create a VM and provision an OS onto it.

## Prerequisites

- [Vagrant](https://www.vagrantup.com/downloads) is installed
- [VirtualBox](https://www.virtualbox.org/) is installed
- A connection to the public internet (air gapped and proxied environments are not supported)

## Steps

1. Clone this repository

   ```bash
   git clone https://github.com/tinkerbell/playground.git
   cd playground
   ```

1. Start the stack

   ```bash
   cd stack/vagrant
   vagrant up
   # This process will take up to 10 minutes depending on your internet connection.
   # It will download HookOS, which is a couple hundred megabytes in size, and an Ubuntu cloud image, which is about 600MB.
   ```

   <details>
   <summary>example output</summary>

   ```bash
   Bringing machine 'stack' up with 'virtualbox' provider...
   ==> stack: Importing base box 'generic/ubuntu2204'...
   ==> stack: Matching MAC address for NAT networking...
   ==> stack: Checking if box 'generic/ubuntu2204' version '4.3.12' is up to date...
   ==> stack: Setting the name of the VM: vagrant_stack_1725555770411_32447
   ==> stack: Clearing any previously set network interfaces...
   ==> stack: Preparing network interfaces based on configuration...
       stack: Adapter 1: nat
       stack: Adapter 2: hostonly
   ==> stack: Forwarding ports...
       stack: 22 (guest) => 2222 (host) (adapter 1)
   ==> stack: Running 'pre-boot' VM customizations...
   ==> stack: Booting VM...
   ==> stack: Waiting for machine to boot. This may take a few minutes...
       stack: SSH address: 127.0.0.1:2222
       stack: SSH username: vagrant
       stack: SSH auth method: private key
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack: Warning: Remote connection disconnect. Retrying...
       stack: Warning: Connection reset. Retrying...
       stack:
       stack: Vagrant insecure key detected. Vagrant will automatically replace
       stack: this with a newly generated keypair for better security.
       stack:
       stack: Inserting generated public key within guest...
       stack: Removing insecure key from the guest if it's present...
       stack: Key inserted! Disconnecting and reconnecting using new SSH key...
   ==> stack: Machine booted and ready!
   ==> stack: Checking for guest additions in VM...
       stack: The guest additions on this VM do not match the installed version of
       stack: VirtualBox! In most cases this is fine, but in rare cases it can
       stack: prevent things such as shared folders from working properly. If you see
       stack: shared folder errors, please make sure the guest additions within the
       stack: virtual machine match the version of VirtualBox you have installed on
       stack: your host and reload your VM.
       stack:
       stack: Guest Additions Version: 6.1.38
       stack: VirtualBox Version: 7.0
   ==> stack: Configuring and enabling network interfaces...
   ==> stack: Mounting shared folders...
       stack: /playground/stack => /home/tink/repos/tinkerbell/playground/stack/vagrant
   ==> stack: Running provisioner: shell...
       stack: Running: /tmp/vagrant-shell20240905-113127-iheh9n.sh
       stack: + main 192.168.56.4 192.168.56.43 08:00:27:9e:f5:3a /playground/stack/ 192.168.56.5 0.4.5 eth1 1.30.4 v5.7.3 v3.15.4 ''
       stack: + local host_ip=192.168.56.4
       stack: + local worker_ip=192.168.56.43
       stack: + local worker_mac=08:00:27:9e:f5:3a
       stack: + local manifests_dir=/playground/stack/
       stack: + local loadbalancer_ip=192.168.56.5
       stack: + local helm_chart_version=0.4.5
       stack: + local loadbalancer_interface=eth1
       stack: + local kubectl_version=1.30.4
       stack: + local k3d_version=v5.7.3
       stack: + local helm_version=v3.15.4
       stack: + update_apt
       stack: + apt-get update
       stack: + DEBIAN_FRONTEND=noninteractive
       stack: + command apt-get --allow-change-held-packages --allow-downgrades --allow-remove-essential --allow-unauthenticated --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold --yes update
       stack: Hit:1 https://mirrors.edge.kernel.org/ubuntu jammy InRelease
       stack: Get:2 https://mirrors.edge.kernel.org/ubuntu jammy-updates InRelease [128 kB]
       stack: Get:3 https://mirrors.edge.kernel.org/ubuntu jammy-backports InRelease [127 kB]
       stack: Get:4 https://mirrors.edge.kernel.org/ubuntu jammy-security InRelease [129 kB]
       stack: Get:5 https://mirrors.edge.kernel.org/ubuntu jammy-updates/main amd64 Packages [1,988 kB]
       stack: Get:6 https://mirrors.edge.kernel.org/ubuntu jammy-updates/main Translation-en [349 kB]
       stack: Get:7 https://mirrors.edge.kernel.org/ubuntu jammy-updates/main amd64 c-n-f Metadata [17.8 kB]
       stack: Get:8 https://mirrors.edge.kernel.org/ubuntu jammy-updates/restricted amd64 Packages [2,386 kB]
       stack: Get:9 https://mirrors.edge.kernel.org/ubuntu jammy-updates/restricted Translation-en [410 kB]
       stack: Get:10 https://mirrors.edge.kernel.org/ubuntu jammy-updates/restricted amd64 c-n-f Metadata [616 B]
       stack: Get:11 https://mirrors.edge.kernel.org/ubuntu jammy-updates/universe amd64 Packages [1,123 kB]
       stack: Get:12 https://mirrors.edge.kernel.org/ubuntu jammy-updates/universe Translation-en [261 kB]
       stack: Get:13 https://mirrors.edge.kernel.org/ubuntu jammy-updates/universe amd64 c-n-f Metadata [26.1 kB]
       stack: Get:14 https://mirrors.edge.kernel.org/ubuntu jammy-updates/multiverse amd64 Packages [43.3 kB]
       stack: Get:15 https://mirrors.edge.kernel.org/ubuntu jammy-updates/multiverse Translation-en [10.8 kB]
       stack: Get:16 https://mirrors.edge.kernel.org/ubuntu jammy-updates/multiverse amd64 c-n-f Metadata [444 B]
       stack: Get:17 https://mirrors.edge.kernel.org/ubuntu jammy-backports/main amd64 Packages [67.8 kB]
       stack: Get:18 https://mirrors.edge.kernel.org/ubuntu jammy-backports/main Translation-en [11.1 kB]
       stack: Get:19 https://mirrors.edge.kernel.org/ubuntu jammy-backports/main amd64 c-n-f Metadata [388 B]
       stack: Get:20 https://mirrors.edge.kernel.org/ubuntu jammy-backports/universe amd64 Packages [28.8 kB]
       stack: Get:21 https://mirrors.edge.kernel.org/ubuntu jammy-backports/universe Translation-en [16.5 kB]
       stack: Get:22 https://mirrors.edge.kernel.org/ubuntu jammy-backports/universe amd64 c-n-f Metadata [672 B]
       stack: Get:23 https://mirrors.edge.kernel.org/ubuntu jammy-security/main amd64 Packages [1,771 kB]
       stack: Get:24 https://mirrors.edge.kernel.org/ubuntu jammy-security/main Translation-en [291 kB]
       stack: Get:25 https://mirrors.edge.kernel.org/ubuntu jammy-security/main amd64 c-n-f Metadata [13.3 kB]
       stack: Get:26 https://mirrors.edge.kernel.org/ubuntu jammy-security/restricted amd64 Packages [2,327 kB]
       stack: Get:27 https://mirrors.edge.kernel.org/ubuntu jammy-security/restricted Translation-en [400 kB]
       stack: Get:28 https://mirrors.edge.kernel.org/ubuntu jammy-security/restricted amd64 c-n-f Metadata [584 B]
       stack: Get:29 https://mirrors.edge.kernel.org/ubuntu jammy-security/universe amd64 Packages [901 kB]
       stack: Get:30 https://mirrors.edge.kernel.org/ubuntu jammy-security/universe Translation-en [176 kB]
       stack: Get:31 https://mirrors.edge.kernel.org/ubuntu jammy-security/universe amd64 c-n-f Metadata [19.2 kB]
       stack: Get:32 https://mirrors.edge.kernel.org/ubuntu jammy-security/multiverse amd64 Packages [37.2 kB]
       stack: Get:33 https://mirrors.edge.kernel.org/ubuntu jammy-security/multiverse Translation-en [7,588 B]
       stack: Get:34 https://mirrors.edge.kernel.org/ubuntu jammy-security/multiverse amd64 c-n-f Metadata [228 B]
       stack: Fetched 13.1 MB in 23s (560 kB/s)
       stack: Reading package lists...
       stack: + install_docker
       stack: + sudo apt-key add -
       stack: + curl -fsSL https://download.docker.com/linux/ubuntu/gpg
       stack: Warning: apt-key is deprecated. Manage keyring files in trusted.gpg.d instead (see apt-key(8)).
       stack: OK
       stack: ++ lsb_release -cs
       stack: + add-apt-repository 'deb https://download.docker.com/linux/ubuntu jammy stable'
       stack: Hit:1 https://mirrors.edge.kernel.org/ubuntu jammy InRelease
       stack: Hit:2 https://mirrors.edge.kernel.org/ubuntu jammy-updates InRelease
       stack: Hit:3 https://mirrors.edge.kernel.org/ubuntu jammy-backports InRelease
       stack: Hit:4 https://mirrors.edge.kernel.org/ubuntu jammy-security InRelease
       stack: Get:5 https://download.docker.com/linux/ubuntu jammy InRelease [48.8 kB]
       stack: Get:6 https://download.docker.com/linux/ubuntu jammy/stable amd64 Packages [38.6 kB]
       stack: Fetched 87.4 kB in 3s (31.8 kB/s)
       stack: Reading package lists...
       stack: W: https://download.docker.com/linux/ubuntu/dists/jammy/InRelease: Key is stored in legacy trusted.gpg keyring (/etc/apt/trusted.gpg), see the DEPRECATION section in apt-key(8) for details.
       stack: Repository: 'deb https://download.docker.com/linux/ubuntu jammy stable'
       stack: Description:
       stack: Archive for codename: jammy components: stable
       stack: More info: https://download.docker.com/linux/ubuntu
       stack: Adding repository.
       stack: Adding deb entry to /etc/apt/sources.list.d/archive_uri-https_download_docker_com_linux_ubuntu-jammy.list
       stack: Adding disabled deb-src entry to /etc/apt/sources.list.d/archive_uri-https_download_docker_com_linux_ubuntu-jammy.list
       stack: + update_apt
       stack: + apt-get update
       stack: + DEBIAN_FRONTEND=noninteractive
       stack: + command apt-get --allow-change-held-packages --allow-downgrades --allow-remove-essential --allow-unauthenticated --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold --yes update
       stack: Hit:1 https://download.docker.com/linux/ubuntu jammy InRelease
       stack: Hit:2 https://mirrors.edge.kernel.org/ubuntu jammy InRelease
       stack: Hit:3 https://mirrors.edge.kernel.org/ubuntu jammy-updates InRelease
       stack: Hit:4 https://mirrors.edge.kernel.org/ubuntu jammy-backports InRelease
       stack: Hit:5 https://mirrors.edge.kernel.org/ubuntu jammy-security InRelease
       stack: Reading package lists...
       stack: W: https://download.docker.com/linux/ubuntu/dists/jammy/InRelease: Key is stored in legacy trusted.gpg keyring (/etc/apt/trusted.gpg), see the DEPRECATION section in apt-key(8) for details.
       stack: + apt-get install --no-install-recommends containerd.io docker-ce docker-ce-cli
       stack: + DEBIAN_FRONTEND=noninteractive
       stack: + command apt-get --allow-change-held-packages --allow-downgrades --allow-remove-essential --allow-unauthenticated --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold --yes install --no-install-recommends containerd.io docker-ce docker-ce-cli
       stack: Reading package lists...
       stack: Building dependency tree...
       stack: Reading state information...
       stack: Suggested packages:
       stack:   aufs-tools cgroupfs-mount | cgroup-lite
       stack: Recommended packages:
       stack:   docker-ce-rootless-extras libltdl7 pigz docker-buildx-plugin
       stack:   docker-compose-plugin
       stack: The following NEW packages will be installed:
       stack:   containerd.io docker-ce docker-ce-cli
       stack: 0 upgraded, 3 newly installed, 0 to remove and 157 not upgraded.
       stack: Need to get 69.5 MB of archives.
       stack: After this operation, 271 MB of additional disk space will be used.
       stack: Get:1 https://download.docker.com/linux/ubuntu jammy/stable amd64 containerd.io amd64 1.7.21-1 [29.5 MB]
       stack: Get:2 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-ce-cli amd64 5:27.2.0-1~ubuntu.22.04~jammy [14.8 MB]
       stack: Get:3 https://download.docker.com/linux/ubuntu jammy/stable amd64 docker-ce amd64 5:27.2.0-1~ubuntu.22.04~jammy [25.3 MB]
       stack: Fetched 69.5 MB in 3s (20.0 MB/s)
       stack: Selecting previously unselected package containerd.io.
   (Reading database ... 76324 files and directories currently installed.)
       stack: Preparing to unpack .../containerd.io_1.7.21-1_amd64.deb ...
       stack: Unpacking containerd.io (1.7.21-1) ...
       stack: Selecting previously unselected package docker-ce-cli.
       stack: Preparing to unpack .../docker-ce-cli_5%3a27.2.0-1~ubuntu.22.04~jammy_amd64.deb ...
       stack: Unpacking docker-ce-cli (5:27.2.0-1~ubuntu.22.04~jammy) ...
       stack: Selecting previously unselected package docker-ce.
       stack: Preparing to unpack .../docker-ce_5%3a27.2.0-1~ubuntu.22.04~jammy_amd64.deb ...
       stack: Unpacking docker-ce (5:27.2.0-1~ubuntu.22.04~jammy) ...
       stack: Setting up containerd.io (1.7.21-1) ...
       stack: Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
       stack: Setting up docker-ce-cli (5:27.2.0-1~ubuntu.22.04~jammy) ...
       stack: Setting up docker-ce (5:27.2.0-1~ubuntu.22.04~jammy) ...
       stack: Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
       stack: Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
       stack: Processing triggers for man-db (2.10.2-1) ...
       stack: NEEDRESTART-VER: 3.5
       stack: NEEDRESTART-KCUR: 5.15.0-91-generic
       stack: NEEDRESTART-KEXP: 5.15.0-91-generic
       stack: NEEDRESTART-KSTA: 1
       stack: + gpasswd -a vagrant docker
       stack: Adding user vagrant to group docker
       stack: + sudo ethtool -K eth1 tx off sg off tso off
       stack: Actual changes:
       stack: tx-scatter-gather: off
       stack: tx-checksum-ip-generic: off
       stack: tx-generic-segmentation: off [not requested]
       stack: tx-tcp-segmentation: off
       stack: + install_kubectl 1.30.4
       stack: + local kubectl_version=1.30.4
       stack: + curl -LO https://dl.k8s.io/v1.30.4/bin/linux/amd64/kubectl
       stack:   % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
       stack:                                  Dload  Upload   Total   Spent    Left  Speed
   100   138  100   138    0     0    129      0  0:00:01  0:00:01 --:--:--   129
   100 49.0M  100 49.0M    0     0  9596k      0  0:00:05  0:00:05 --:--:-- 14.0M
       stack: + chmod +x ./kubectl
       stack: + mv ./kubectl /usr/local/bin/kubectl
       stack: + run_helm 192.168.56.4 192.168.56.43 08:00:27:9e:f5:3a /playground/stack/ 192.168.56.5 0.4.5 eth1 v5.7.3 v3.15.4
       stack: + local host_ip=192.168.56.4
       stack: + local worker_ip=192.168.56.43
       stack: + local worker_mac=08:00:27:9e:f5:3a
       stack: + local manifests_dir=/playground/stack/
       stack: + local loadbalancer_ip=192.168.56.5
       stack: + local helm_chart_version=0.4.5
       stack: + local loadbalancer_interface=eth1
       stack: + local k3d_version=v5.7.3
       stack: + local namespace=tink-system
       stack: + local helm_version=v3.15.4
       stack: + install_k3d v5.7.3
       stack: + local k3d_Version=v5.7.3
       stack: + wget -q -O - https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh
       stack: + TAG=v5.7.3
       stack: + bash
       stack: Preparing to install k3d into /usr/local/bin
       stack: k3d installed into /usr/local/bin/k3d
       stack: Run 'k3d --help' to see what you can do with it.
       stack: + start_k3d
       stack: + K3D_FIX_DNS=false
       stack: + k3d cluster create --network host --no-lb --k3s-arg --disable=traefik,servicelb,metrics-server,local-storage
       stack: INFO[0000] [SimpleConfig] Hostnetwork selected - disabling injection of docker host into the cluster, server load balancer and setting the api port to the k3s default
       stack: INFO[0000] [ClusterConfig] Hostnetwork selected - disabling injection of docker host into the cluster, server load balancer and setting the api port to the k3s default
       stack: WARN[0000] No node filter specified
       stack: INFO[0000] Prep: Network
       stack: INFO[0000] Re-using existing network 'host' (d91c8cbfbba180401b621eac5153edbbdda1e1c3181fa640dc5ac6b77eec1779)
       stack: INFO[0000] Created image volume k3d-k3s-default-images
       stack: INFO[0000] Starting new tools node...
       stack: INFO[0001] Creating node 'k3d-k3s-default-server-0'
       stack: INFO[0001] Pulling image 'ghcr.io/k3d-io/k3d-tools:5.7.3'
       stack: INFO[0003] Pulling image 'docker.io/rancher/k3s:v1.30.3-k3s1'
       stack: INFO[0004] Starting node 'k3d-k3s-default-tools'
       stack: INFO[0011] Using the k3d-tools node to gather environment information
       stack: INFO[0011] Starting cluster 'k3s-default'
       stack: INFO[0011] Starting servers...
       stack: INFO[0011] Starting node 'k3d-k3s-default-server-0'
       stack: INFO[0014] All agents already running.
       stack: INFO[0014] All helpers already running.
       stack: INFO[0014] Cluster 'k3s-default' created successfully!
       stack: INFO[0014] You can now use it like this:
       stack: kubectl cluster-info
       stack: + mkdir -p /root/.kube/
       stack: + k3d kubeconfig get -a
       stack: + kubectl wait --for=condition=Ready nodes --all --timeout=600s
       stack: node/k3d-k3s-default-server-0 condition met
       stack: + kubectl_for_vagrant_user
       stack: + runuser -l vagrant -c 'mkdir -p ~/.kube/'
       stack: + runuser -l vagrant -c 'k3d kubeconfig get -a > ~/.kube/config'
       stack: + chmod 600 /home/vagrant/.kube/config
       stack: + echo 'export KUBECONFIG="/home/vagrant/.kube/config"'
       stack: + install_helm v3.15.4
       stack: + local helm_ver=v3.15.4
       stack: + curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
       stack: + chmod 700 get_helm.sh
       stack: + ./get_helm.sh --version v3.15.4
       stack: Downloading https://get.helm.sh/helm-v3.15.4-linux-amd64.tar.gz
       stack: Verifying checksum... Done.
       stack: Preparing to install helm into /usr/local/bin
       stack: helm installed into /usr/local/bin/helm
       stack: + helm_install_tink_stack tink-system 0.4.5 eth1 192.168.56.5
       stack: + local namespace=tink-system
       stack: + local version=0.4.5
       stack: + local interface=eth1
       stack: + local loadbalancer_ip=192.168.56.5
       stack: + trusted_proxies=
       stack: + '[' '' '!=' '' ']'
       stack: ++ kubectl get nodes -o 'jsonpath={.items[*].spec.podCIDR}'
       stack: ++ tr ' ' ,
       stack: + trusted_proxies=
       stack: + sleep 5
       stack: + '[' '' '!=' '' ']'
       stack: ++ kubectl get nodes -o 'jsonpath={.items[*].spec.podCIDR}'
       stack: ++ tr ' ' ,
       stack: + trusted_proxies=
       stack: + sleep 5
       stack: + '[' '' '!=' '' ']'
       stack: ++ kubectl get nodes -o 'jsonpath={.items[*].spec.podCIDR}'
       stack: ++ tr ' ' ,
       stack: + trusted_proxies=
       stack: + sleep 5
       stack: + '[' '' '!=' '' ']'
       stack: ++ kubectl get nodes -o 'jsonpath={.items[*].spec.podCIDR}'
       stack: ++ tr ' ' ,
       stack: + trusted_proxies=10.42.0.0/24
       stack: + sleep 5
       stack: + '[' 10.42.0.0/24 '!=' '' ']'
       stack: + helm install tink-stack oci://ghcr.io/tinkerbell/charts/stack --version 0.4.5 --create-namespace --namespace tink-system --wait --set 'smee.trustedProxies={10.42.0.0/24}' --set 'hegel.trustedProxies={10.42.0.0/24}' --set stack.kubevip.interface=eth1 --set stack.relay.sourceInterface=eth1 --set stack.loadBalancerIP=192.168.56.5 --set smee.publicIP=192.168.56.5
       stack: Pulled: ghcr.io/tinkerbell/charts/stack:0.4.5
       stack: Digest: sha256:0d2ba4fa96bd6bcbc39cfd63a85af2f17d59538a5573ff37bb8bf48fedd0659f
       stack: NAME: tink-stack
       stack: LAST DEPLOYED: Thu Sep  5 17:06:42 2024
       stack: NAMESPACE: tink-system
       stack: STATUS: deployed
       stack: REVISION: 1
       stack: TEST SUITE: None
       stack: + apply_manifests 192.168.56.43 08:00:27:9e:f5:3a /playground/stack/ 192.168.56.5 tink-system
       stack: + local worker_ip=192.168.56.43
       stack: + local worker_mac=08:00:27:9e:f5:3a
       stack: + local manifests_dir=/playground/stack/
       stack: + local host_ip=192.168.56.5
       stack: + local namespace=tink-system
       stack: + disk_device=/dev/sda
       stack: + lsblk
       stack: + grep -q vda
       stack: + export DISK_DEVICE=/dev/sda
       stack: + DISK_DEVICE=/dev/sda
       stack: + export TINKERBELL_CLIENT_IP=192.168.56.43
       stack: + TINKERBELL_CLIENT_IP=192.168.56.43
       stack: + export TINKERBELL_CLIENT_MAC=08:00:27:9e:f5:3a
       stack: + TINKERBELL_CLIENT_MAC=08:00:27:9e:f5:3a
       stack: + export TINKERBELL_HOST_IP=192.168.56.5
       stack: + TINKERBELL_HOST_IP=192.168.56.5
       stack: + for i in "$manifests_dir"/{hardware.yaml,template.yaml,workflow.yaml}
       stack: + envsubst
       stack: + echo -e ---
       stack: + for i in "$manifests_dir"/{hardware.yaml,template.yaml,workflow.yaml}
       stack: + envsubst
       stack: + echo -e ---
       stack: + for i in "$manifests_dir"/{hardware.yaml,template.yaml,workflow.yaml}
       stack: + envsubst
       stack: + echo -e ---
       stack: + kubectl apply -n tink-system -f /tmp/manifests.yaml
       stack: hardware.tinkerbell.org/machine1 created
       stack: template.tinkerbell.org/ubuntu created
       stack: workflow.tinkerbell.org/playground-workflow created
       stack: + kubectl apply -n tink-system -f /playground/stack//ubuntu-download.yaml
       stack: configmap/download-image created
       stack: job.batch/download-ubuntu-noble created
       stack: all done!
       stack: + echo 'all done!'
   ```

   </details>

1. Wait for HookOS and Ubuntu image to be downloaded

   ```bash
   vagrant ssh stack
   kubectl get jobs -n tink-system --watch
   exit
   # There are 2 Kubernetes jobs that run to download HookOS and the Ubuntu image.
   # Once both jobs are complete exit the stack VM.
   ```

   <details>
   <summary>example output</summary>

   ```bash
   NAME                    STATUS     COMPLETIONS   DURATION   AGE
   download-hook           Complete   1/1           39s        42s
   download-ubuntu-noble   Running    0/1           8s         8s
   download-ubuntu-noble   Running    0/1           74s        74s
   download-ubuntu-noble   Running    0/1           75s        75s
   download-ubuntu-noble   Complete   1/1           75s        75s
   ```

   </details>

1. Start the machine to be provisioned

   ```bash
   vagrant up machine1
   # This will start a VM to pxe boot. A GUI window of this machines console will be opened.
   # The `vagrant up machine1` command will exit quickly and show the following error message. This is expected.
   # Once the command line control is returned to you, you can move on to the next step.
   ```

   <details>
   <summary>example output</summary>

   ```bash
   Bringing machine 'machine1' up with 'virtualbox' provider...
   ==> machine1: Checking if box 'jtyr/pxe' version '2' is up to date...
   ==> machine1: Fixed port collision for 22 => 2222. Now on port 2200.
   ==> machine1: Clearing any previously set network interfaces...
   ==> machine1: Preparing network interfaces based on configuration...
       machine1: Adapter 1: hostonly
   ==> machine1: Forwarding ports...
       machine1: 22 (guest) => 2200 (host) (adapter 1)
       machine1: VirtualBox adapter #1 not configured as "NAT". Skipping port
       machine1: forwards on this adapter.
   ==> machine1: Running 'pre-boot' VM customizations...
   ==> machine1: Booting VM...
   ==> machine1: Waiting for machine to boot. This may take a few minutes...
       machine1: SSH address: 127.0.0.1:22
       machine1: SSH username: vagrant
       machine1: SSH auth method: private key
       machine1: Warning: Authentication failure. Retrying...
   Timed out while waiting for the machine to boot. This means that
   Vagrant was unable to communicate with the guest machine within
   the configured ("config.vm.boot_timeout" value) time period.

   If you look above, you should be able to see the error(s) that
   Vagrant had when attempting to connect to the machine. These errors
   are usually good hints as to what may be wrong.

   If you're using a custom box, make sure that networking is properly
   working and you're able to connect to the machine. It is a common
   problem that networking isn't setup properly in these boxes.
   Verify that authentication configurations are also setup properly,
   as well.

   If the box appears to be booting properly, you may want to increase
   the timeout ("config.vm.boot_timeout") value.
   ```

   </details>

1. Watch the provision complete

   ```bash
   # log in to the stack VM
   vagrant ssh stack

   # watch for the workflow to complete
   # once the workflow is complete (see the example output below for completion), move on to the next step
   kubectl get -n tink-system workflow playground-workflow --watch
   ```

   <details>
   <summary>example output</summary>

   ```bash
   NAME                  TEMPLATE   STATE
   playground-workflow   ubuntu     STATE_PENDING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_RUNNING
   playground-workflow   ubuntu     STATE_SUCCESS
   ```

   </details>

1. Login to the machine

   The machine has been provisioned with Ubuntu.
   You can now SSH into the machine.

   ```bash
   ssh tink@192.168.56.43 # user/pass => tink/tink
   ```
