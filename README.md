# Heist Example

Basic unprivileged setup.

1. Edit the roster file for your hosts.
2. Edit the etc/salt/master file for the location of this repo.
3. Open three terminals and run the commands below:

## Terminal 1
```bash
curl -LO https://repo.saltstack.com/salt-bin/linux/salt
chmod 755 salt
./salt master -c etc/salt -l info
```

## Terminal 2
```bash
python3 -m venv env
pip3 install heist mock
heist -c etc/heist/heist.conf -R roster
```

## Terminal 3
``` bash
./salt key -c etc/salt -A
./salt -c etc/salt \* test.version
```
