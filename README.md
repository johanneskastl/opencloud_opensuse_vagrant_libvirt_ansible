# opencloud_opensuse_vagrant_libvirt_ansible

Vagrant-libvirt setup that runs the [OpenCloud
Server](https://github.com/opencloud-eu/opencloud) based on the openSUSE package
that I am currently working on.

This `main` branch uses openSUSE Leap 15.6 as operating system. The OS can be
changed in the Vagrantfile. Please be aware, that this might break the Ansible
provisioning.

## WORK IN PROGRESS

**Attention**

The package is currently under heavy development.

## Vagrant

1. You need `vagrant`, obviously. And `git`. And Ansible...
1. Fetch the box, per default this is `opensuse/Leap-15.6.x86_64`, using
   `vagrant box add opensuse/Leap-15.6.x86_64`.
1. Make sure the git submodules are fully working by issuing
   `git submodule init && git submodule update`
1. Run `vagrant up`
1. Ansible prints out the OpenCloud URL and the credentials at the
   end of the provisioning step:

   ```
   TASK [OpenCloud URL] ***********************************************************
   ok: [opencloud-quickstart] => {
       "msg": "Opencloud will reachable here: https://192.0.2.13:9200 (using a self-signed certificate)"
   }

   TASK [OpenCloud credentials] ***************************************************
   ok: [opencloud-quickstart] => {
       "msg": "Log in as user 'admin' with the password 'atotallysecurepassword'"
   }
   ```

1. Open the URL in your browser, accept the self-signed certificate and log in
   using the username `admin` and the password `atotallysecurepassword`.
1. Party!

## Cleaning up

The VM can be torn down after playing around using `vagrant destroy`.

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
