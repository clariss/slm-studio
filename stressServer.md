get package stress
```
apt-get install stress
```

send command to stress CPU load averages
```
stress --cpu 2 --io 1 --vm 1 --vm-bytes 128M --timeout 120s --verbose
```