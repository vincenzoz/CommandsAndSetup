# Windows commands

* [Processes](#Processes)
* [Dual boot](#Dual-boot-GRUB-missing)

## Processes

### Find specific service

```txt
tasklist | findstr java
```

### Check and kill process running on specific port

```txt
netstat -ano | findstr :8080
taskkill /PID <process_id> /F
```

### Kill windows service

### e.g. kill the 'Wildfly' service stucked on Windows services list

```txt
Find the process name ex. Wildfly

Windows > services > Rigth click on the service -> Properties -> Service name: Wildfly

sc queryex Wildfly
(sc: service control, queryEx: Show extended info - pid, flags)

The process info will be displayed, with the PID

taskkill /PID <process_id> /F

Refresh the Service list
```

### Delete windows  service

```txt
sc delete ActiveMQ
```

## Dual boot GRUB missing

### After windows updates, dual boot doesn't show the ubuntu GRUB bios anymore

```txt
Restart windows
Press F10 to enter on bios
Bios order (Find EFI Boot Manager)
OS mode - change the order using ubuntu first on os
```
