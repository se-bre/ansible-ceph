## ceph buildup and remove role

**tested OS:**
 - arch linux (VM 64bit)  
 - ubuntu aarch64  

**Hardware:**
 - Hardkernel [Odroid-C2](http://www.hardkernel.com/main/products/prdt_info.php?g_code=G145457216438)  

---

### description

this role will create or remove a ceph cluster  

by default it will create the cluster or add new hosts to the cluster  

**Hint:**  
 - to add new OSD Hosts to your cluster limit the role to run only on this host  
 - if you use filestore you can safely run it over already configured hosts!  

**buildup:**  
 - role turn **all** unused blockdevices into OSDs (if host is in group ceph_osd_hosts)  
 - all defined mon hosts get a mgr  
 - default pg/pgp size for pools is 128  
 - for each client role creates a rbd-device in pool images with name: <hostname>  
 - rbd-device will get ext4 fs and mounted on `/mnt/rbd` (not reboot persistent)  

 **remove cluster:**
  - role will destroy complete cluster!  
  - all OSDs will be destroyed  
  - all RBD devices will be unmounted on clients  
  - all mons/mgrs will be destroyed  

---

### default vars

`ceph_release:` choose your ceph release  
`ceph_first_mon:` define hostname of your first ceph mon to start buildup cluster  
`ceph_mons:` define ceph mons  
`ceph_osd_format:` bluestore or filestore  

***Hint:*** bluestore won't work with arch linux  

`ceph_public_net:` client network  
`ceph_cluster_net:` replication network  
`ceph_remove_cluster:` set to True to remove cluster (extra-var **yes_i_really_really_mean_it** has to be True as well to remove cluster! )  
`ceph_buildup_cluster:` to create cluster + add new hosts  
`ceph_mgr_modules:` mgr modules should be enabled on `ceph_first_mon`  
`ceph_pools:` pools to create  
