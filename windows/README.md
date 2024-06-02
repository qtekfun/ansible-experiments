# Windows Remote Host

To be able to use the Ansible's WinRM module you will need this to be run in the remote server.

## Enable WinRM

``` powershell
Enable-PSRemoting -Force
```

## Allow Unencrypted traffic (Optional, depending on your security requirements)

``` powershell
Set-Item WSMan:\localhost\Service\AllowUnencrypted $true
```

## Allow Basic Authentication (Optional, depending on your security requirements)

``` powershell
Set-Item WSMan:\localhost\Service\Auth\Basic $true
```

## Set WinRM to auto-start

``` powershell
Set-Service WinRM -StartMode Automatic
```

## Create a WinRM listener

``` powershell
New-Item -Path WSMan:\localhost\Listener -Transport HTTP -Address * -Force
```

## Run the playbook

``` powershell
ansible-playbook -i <host file> <playbook name>
```
