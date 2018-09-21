# Go and Sudo

Using Gopacket to sniff the interfaces requires superuser privileges.
But, my `gopath` under root is set to `/root/go` which will not run
my scripts located in the `$HOME/go` folder. To ameliorate this without 
altering the Sudoers use `sudo -E`.

**sudo -E** from the man pages.
```shell

-E, --preserve-ev
          Indicates to the security policy that the user wishes to pre‐
          serve their existing environment variables.  The security
          policy may return an error if the user does not have permis‐
          sion to preserve the environment.

```

