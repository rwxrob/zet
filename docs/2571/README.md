# Install RedHat Ansible Configuration Manager

There are two different main approaches, with and without access to the Internet. These notes are for using `reposync` to create an "offline" installation from RPMs with dependencies.

```sh
sudo subscription-manager repos --enable rhel-9-for-aarch64-baseos-rpms --enable rhel-9-for-aarch64-appstream-rpms
sudo dnf install yum-utils
sudo reposync -m --download-metadata --gpgcheck  -p /path/to/download
```

Note that reposync requires a huge amount of bandwidth and preferrably speed. Not something to try with less than 100mbps connection.


Related:

* <https://docs.redhat.com/en/documentation/red_hat_ansible_automation_platform/2.4/html/red_hat_ansible_automation_platform_installation_guide/disconnected-installation#proc-synchronizing-rpm-repositories-by-using-reposync_disconnected-installation>
