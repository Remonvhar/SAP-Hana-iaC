# IP addresses auto generation

In order to facilitate the configuration of the project, the IP addresses of the machines can be auto generated, based on the used network address range. To use the auto generation, just don't use any of the variables of the project that are used to set the address to the machines (e.g. `hana_ips`, `hana_cluster_vip`, `netweaver_ips`, etc)

**Note:** If you are specifying the IP addresses manually, make sure these are valid IP addresses. They should not be currently in use by existing instances. 

## Azure

Example based on `10.74.0.0/16` vnet address range and `10.74.0.0/24` subnet address range:

| Name | Substituted variable | Addresses | Comments |
| :---: | :---: | :----: | :---: |
| Iscsi server | `iscsi_srv_ip` | `10.74.0.4` ||
| Monitoring | `monitoring_srv_ip` | `10.74.0.5` ||
| Hana ips | `hana_ips` | `10.74.0.10`, `10.74.0.11` ||
| Hana cluster vip | `hana_cluster_vip` | `10.74.0.12` | Only used if HA is enabled in HANA |
| Hana cluster vip secondary | `hana_cluster_vip_secondary` | `10.74.0.13` | Only used if the Active/Active setup is used |
| DRBD ips | `drbd_ips` | `10.74.0.20`, `10.74.0.21` ||
| DRBD cluster vip | `drbd_cluster_vip` | `10.74.0.22` ||
| Netweaver ips | `netweaver_ips` | `10.74.0.30`, `10.74.0.31`, `10.74.0.32`, `10.74.0.33` | Addresses for the ASCS, ERS, PAS and AAS. The sequence will continue if there are more AAS machines |
| Netweaver virtual ips | `netweaver_virtual_ips` | `10.74.0.34`, `10.74.0.35`, `10.74.0.36`, `192.168.135.37` | The 1st virtual address will be the next in the sequence of the regular Netweaver addresses |
