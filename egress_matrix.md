Egress Matrix
=============

The chart below compares the various egress options

|                     | Host       | Static IP   | Firewall     | Router    | IPTables   |
| ------------------- | ---------- | ----------- | ----------   | --------- | ---------- |
| 1. Self Healing     | Yes        | No          | Yes          | Yes[^1]   | Yes[^2]    |
| 2. Multipath        | Yes        | No          | Yes          | No        | Yes[^2]    |
| 3. Src IP           | Host IP    | Egress IP   | Host IP      | Egress IP | Any        |
| 4. Dst IPs          | Any        | Any         | Assigned[^4] | Assigned  | Any        |
| 5. Level Used[^3]   | Built-in   | Cluster     | Project      | Project   | Host       |
| 6. RH Supported     | Yes        | Yes         | Yes          | Yes       | No         |


1. **Self Healing** - In the event of a failure, OpenShift will take action automatically to restore service
2. **multipath** - Egress will happen from multiple points i.e. not tunneled to a single point 
3. **Src IP** - How the IP will be determined
4. **Dst IP** -



[^1]: There are caveats here that need worked through to ensure this works as advertised
[^2]: Possible but extra work is needed
[^3]: Some of these may be applied at multiple levels
[^4]: Broad support for controlling destion
