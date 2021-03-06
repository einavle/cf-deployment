# Backup and Restore ops-files

This is the README for Backup and Restore Ops-files. Use these to configure your deployment for use with [BBR](https://github.com/cloudfoundry-incubator/bosh-backup-and-restore).
For more information about using these ops-files, see [the Cloud Foundry docs](https://docs.cloudfoundry.org/bbr/cf-backup.html).
To learn more about `cf-deployment`, go to the main [README](../../README.md).

- For General Ops-files, check out the [Ops-file README](../README.md).
- For Addons Ops-files that can be applied to manifests or runtime configs, check out the [Addons Ops-file README](../addons/README.md).
- For Bits Service Ops-files (for configuring your deployment for use with [Bits Service](https://github.com/cloudfoundry-incubator/bits-service)), checkout the [Bits Service Ops-files README](../bits-service/README.md).
- For Community Ops-files, check out the [Community Ops-file README](../community/README.md).
- For Legacy Ops-files, checkout the [Legacy Ops-file README](../legacy/README.md).
- For Experimental Ops-files, check out the [Experimental Ops-file README](../experimental/README.md).

## Ops-Files

| Name | Purpose | Notes |
|:---  |:---     |:---   |
| [`enable-backup-restore.yml`](enable-backup-restore.yml) | Deploy BOSH backup and restore instance and enable release level backup. | |
| [`enable-backup-restore-azure.yml`](enable-backup-restore-azure.yml) | Enables the backup and restore of Azure blobstores with soft delete enabled. | Requires `enable-backup-restore.yml` and `use-azure-storage-blobstore.yml` |
| [`enable-restore-azure-clone.yml`](enable-restore-azure-clone.yml) | Deploy with this ops file when restoring to a different Azure storage account. | Requires `enable-backup-restore.yml` and `use-azure-storage-blobstore.yml` |
| [`enable-backup-restore-gcs.yml`](enable-backup-restore-gcs.yml) | Enables the backup and restore of GCS blobstores. | Requires `enable-backup-restore.yml`  and `use-gcs-blobstore-service-account.yml` |
| [`enable-backup-restore-s3-versioned.yml`](enable-backup-restore-s3-versioned.yml) | Enables the backup and restore of versioned S3 blobstores. | Requires `enable-backup-restore.yml` and `use-s3-blobstore.yml` |
| [`enable-backup-restore-s3-unversioned.yml`](enable-backup-restore-s3-unversioned.yml) | Enables the backup and restore of unversioned S3 blobstores. | Requires `enable-backup-restore.yml` and `use-s3-blobstore.yml`. Introduces [new variables](example-vars-files/vars-enable-backup-restore-s3-unversioned.yml) |
| [`enable-backup-restore-nfs-broker.yml`](enable-backup-restore-nfs-broker.yml) | Deploy BOSH backup and restore scripts for the NFS service broker. | Requires `enable-backup-restore.yml` and `operations/enable-nfs-volume-service.yml`. |
| [`skip-backup-restore-droplets.yml`](skip-backup-restore-droplets.yml) | Skips the droplets bucket from the blobstore backup | Requires `enable-backup-restore.yml` and can only be used with an external blobstore. |
| [`skip-backup-restore-droplets-and-packages.yml`](skip-backup-restore-droplets-and-packages.yml) | Skips the droplets and the packages buckets from the blobstore backup | Requires `enable-backup-restore.yml` and can only be used with an external blobstore. |
