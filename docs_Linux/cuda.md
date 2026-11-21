# CUDA Settings

```
dnf install kernel-devel-[xxx] kernel-headers-[xxx] gcc make dkms epel-release
dnf config-manager --add-repo https://developer.download.nvidia.com/compute/cuda/repos/rhel10/x86_64/cuda-rhel10.repo
dnf clean all
dnf -y install cuda
nvidia-smi
```
