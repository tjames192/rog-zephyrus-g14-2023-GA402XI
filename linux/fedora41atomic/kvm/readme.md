# cpu pinning

| 0 | 1 |  2 |  3 |  4 |  5 |  6 |  7 |
| - | - |  - |  - |  - |  - |  - |  - |
| 0 | 1 |  2 |  3 |  4 |  5 |  6 |  7 |
| 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |

```
<vcpu placement='static'>16</vcpu>
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
    <vcpupin vcpu='8' cpuset='16'/>
    <vcpupin vcpu='9' cpuset='17'/>
    <vcpupin vcpu='10' cpuset='18'/>
    <vcpupin vcpu='11' cpuset='19'/>
    <vcpupin vcpu='12' cpuset='20'/>
    <vcpupin vcpu='13' cpuset='21'/>
    <vcpupin vcpu='14' cpuset='22'/>
    <vcpupin vcpu='15' cpuset='23'/>
    <emulatorpin cpuset='8-15,24-31'/>
    <iothreadpin iothread='1' cpuset='8-15'/>
    <iothreadpin iothread='2' cpuset='24-31'/>
  </cputune>
```
