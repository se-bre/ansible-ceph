## ceph buildup and remove role

---

### default vars

`ceph_release:` choose your ceph release  
`ceph_first_mon:` define hostname of your first ceph mon to start buildup cluster  
`ceph_mons:` define ceph mons  
`ceph_osd_format:` bluestore or filestore  

***Hint:*** bluestore won't work with arch linux  

`ceph_public_net:` client network  
`ceph_cluster_net:` replication network  
`ceph_remove_cluster:` set to True to remove cluster (extra-var yes_i_really_really_mean_it has to be True as well to remove cluster! )  
`ceph_buildup_cluster:` to create cluster + add new hosts  
`ceph_mgr_modules:` mgr modules should be enabled on `ceph_first_mon`  
`ceph_pools:` pools to create  
