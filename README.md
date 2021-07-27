# ansible-role-gateway
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![CI](https://github.com/jesmigel/ansible-role-gateway/actions/workflows/build.yaml/badge.svg?branch=main)](https://github.com/jesmigel/ansible-role-gateway/actions/workflows/build.yaml)

Ansible role for setting up a gateway host

### References
| Name | Comments |
| - | - |
| [Dependencies](https://github.com/jesmigel/ansible-role-common#dependencies) | Deployment Toolchain |
| [Make Commands](https://github.com/jesmigel/ansible-role-common#make-commands) | Deployment Shortcuts |
| [Preflight Steps](https://github.com/jesmigel/ansible-role-common#preflieght-steps) | Pre deployment configuration 
|||

### [Variables](./defaults/main.yaml)
| Name | Comments |
| --- | --- |
| `gateway_binaries` | Binaries required for setting up a gateway host |
| `handler_list` | List of ansible task handlers |
| `config` | Contains a dictionary of network interfaces to be configured. |
| `timezone` | Country/City timezone |
| | |

### ToDo
- Variable structure breakdown