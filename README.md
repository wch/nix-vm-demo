
To build the VM:

```
nix build  ./#nixosConfigurations.vm.config.system.build.vm
```

Run the VM headless and map localhost:2222 to port 22 in the VM:

```
QEMU_NET_OPTS="hostfwd=tcp::2222-:22" result/bin/run-nixos-vm -display none
```

Then, from the host, log in (password is `guest`):

```
ssh localhost -p 2222 -l guest
```

