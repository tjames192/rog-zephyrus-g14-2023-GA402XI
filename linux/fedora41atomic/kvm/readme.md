# cpu pinning

| core # | 0 | 1 |  2 |  3 |  4 |  5 |  6 |  7 |
| -  | - | - |  - |  - |  - |  - |  - |  - |
| P# | 0 | 1 |  2 |  3 |  4 |  5 |  6 |  7 |
| P# | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |

```
<vcpu placement='static'>14</vcpu>
  <iothreads>2</iothreads>
  <cputune>
    <vcpupin vcpu='0' cpuset='0'/>
    <vcpupin vcpu='1' cpuset='1'/>
    <vcpupin vcpu='2' cpuset='2'/>
    <vcpupin vcpu='3' cpuset='3'/>
    <vcpupin vcpu='4' cpuset='4'/>
    <vcpupin vcpu='5' cpuset='5'/>
    <vcpupin vcpu='6' cpuset='6'/>
    <vcpupin vcpu='7' cpuset='7'/>
    <vcpupin vcpu='8' cpuset='8'/>
    <vcpupin vcpu='9' cpuset='9'/>
    <vcpupin vcpu='10' cpuset='10'/>
    <vcpupin vcpu='11' cpuset='11'/>
    <vcpupin vcpu='12' cpuset='12'/>
    <vcpupin vcpu='13' cpuset='13'/>
    <emulatorpin cpuset='6-7,14-15'/>
    <iothreadpin iothread='1' cpuset='6-7'/>
    <iothreadpin iothread='2' cpuset='14-15'/>
  </cputune>
```
