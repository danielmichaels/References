# VBoxManage commands

Basic commands to run Virtual Box VM's from the cli.

Requires the extension pack to be installed first.

**List all Virtual Machines**

```VBoxManage list vms```

**Start a VM**

```shell
# start desktop
VBoxManage startvm "name of vm"

# start headless
VBoxManage startvm "name of vm" --type headless
```

**Pause a started VM**

```VBoxManage controlvm "name of vm" pause [--type headless]```

**Restart a paused VM**

```VBoxManage controlvm "name of vm" resume [--type headless]```

**Shut down the VM**
  
```VBoxManage controlvm "name of vm" poweroff [--type headless]```
