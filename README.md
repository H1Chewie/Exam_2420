## 2420 Linux System Administration Final Exam

#### Part 1
Use the following code to update software on Ubuntu OS

    sudo apt upgrade
    sudo apt update

#### Part 2

```
vim part2
esc + : + set number to show line numbers
enter + line number + shift g to move to the different lines
/V to jump to the line 2 where V needs to be changed to C
/V to jump to line 5 where it needs to be changed to C
/digit to jump to line 10 to change numb to digit

```

![file edit](./images/part1.png)

#### Part 3

```
man journalctl
```
![file edit](./images/part2.png)

```
/output
```
![man search](./images/part3.png)

```
journalctl -b --output=json-pretty -p 4
```
#### Part 4

```

```

#### Part 5

![service](./images/part5.png)

The service file is located in /etc/systemd/system.

Service File:
```
[Unit]
Description=Create file to greet Bob

[Service]
Type=oneshot
ExecStart=/bin/bash -c 'echo "hi Bob" > /home/vagranthi-bob'

[Install]
WantedBy=multi-user.target
```

#### Part 6


![timer](./images/part6.png)
(Please ignore the part where I forgot to systemctl 🙏)

```
[Unit]
Description=Create file to greet Bob
Requires=part5.service

[Timer]
OnBootSec=1min
OnUnitActiveSec=1d

[Install]
WantedBy=timers.target
```
