### ceph buildup and remove role

#### default vars

__ceph_release:__ choose your ceph release  

__ceph_first_mon:__ define hostname of your first ceph mon to start buildup cluster  

__ceph_mons:__ define ceph mons  

__ceph_osd_format:__ bluestore or filestore  

***Hint:*** bluestore won't work with arch linux  

__ceph_public_net:__ client network  
__ceph_cluster_net:__ replication network  

__ceph_remove_cluster:__ set to True to remove cluster (extra-var yes_i_really_really_mean_it has to be True as well to remove cluster! )  
__ceph_buildup_cluster:__ to create cluster + add new hosts  

__ceph_mgr_modules:__ mgr modules should be enabled on `ceph_first_mon`  

__ceph_pools:__ pools to create
