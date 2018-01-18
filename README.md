# icinga2-plugin-zfssnapshots
Check and count snapshots, check their age
* Tested on Solaris only
* GNU tools hardcoded (may change in further releases)
* Status **worksforme**

### Usage
```
zfs_snapshots.sh [ -c <critical_hours> ] [ -w <warning_hours> ] -d <dataset>
  -c : Optional: CRITICAL snapshot age in hours (default: 12h)
  -d : dataset to check"
  -w : Optional: WARNING snapshot age in hours (default: 6h)
```

### Example
```
./zfs_snapshots.sh -d Data01/archives
OK: got snapshot(s) for Data01/archives within the last 6 hours.
Creation of last snapshot: January 18, 2018 at 10:15:00 AM CET (timezone is Europe/Berlin)

  - 40 hourly snapshot(s) for Data01/archives
  - 7 daily snapshot(s) for Data01/archives
  - 3 weekly snapshot(s) for Data01/archives
  - 1 monthly snapshot(s) for Data01/archives
  - 1 yearly snapshot(s) for Data01/archives
|last_ago=641;21600;43200;0;43200; hourly=40;;;;; daily=7;;;;; weekly=3;;;;; monthly=1;;;;; yearly=1;;;;;
```
