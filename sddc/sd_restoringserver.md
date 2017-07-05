---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Restoring management components for Cloud Foundation instances

When failures occur on your management components, you can restore the management components to a previous backup. 

## Before you begin

Ensure that the instance has at least one backup to restore from.

**Note**: A restore process restores the management components from a backup image that you created before. Because the configuration of the ESXi server is not backed up, you cannot fully recover configurations that exist in both management components and ESXi servers.

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Ensure that you are on the **Cloud Foundation** tab.
2. Click the instance to restore.
3. Click the **Backup and Restore** tab.
4. Select a backup image to restore from by clicking a backup job entry in the **Restore Points** section.
5. Click **Restore** to start the restore process of the management virtual machines.

## Results

When you start a job for restoring management components, you open a ticket to IBM® Support. IBM Support works with you to complete the 
restore job, including the restore of the NSX configuration, if applicable.

You can click **Refresh** to track the restore progress. When the restore job is completed, you recover the management components to the backup image that you selected.

## Related links

* [Backing up management components for Cloud Foundation instances](sd_backingupserver.html)
