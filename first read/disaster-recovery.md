
# disaster recovery
---

---
>[!abstract] Terms:
>- RTO: time it takes to restore business to service level after a disruption
>- RPO: acceptable amount of data loss measured in time before disaster occurs
## Backup and Restore %% fold %%
- store backup data on [[storage-s3#^939999|S3]] to restore quickly
## Pilot Light %% fold %%
- quicker recovery time since core pieces of the system are already running and kept up to date
## Warm Standby Solution %% fold %%
- scaled down version of fully functional environment is always running in the cloud
## Multi-site Solution %% fold %%
- run your infra on another site in an active configuration
- use multiple [[AWS-Regions-and-Availability-Zones.jpg|AZs]]
---
# References
- [disaster recovery cheat sheet](https://tutorialsdojo.com/aws-well-architected-framework-disaster-recovery/)
# Tags
- #aws-ccp-exam-notes/overview/disaster-recovery 

---