---
layout: default
title: Snapshot management
parent: Opensearch Dashboard
# grand_parent: Log Analytics
nav_order: 30
---

# Snapshot management

You can set up Snapshot Management (SM) in OpenSearch Dashboards.

[Snapshots](https://opensearch.org/docs/latest/opensearch/snapshots/index/)  are backups of a cluster’s indexes and state. The state includes cluster settings, node information, index metadata (mappings, settings, templates), and shard allocation.

Snapshots have two main uses:

1.  Recovering from failure
    
    For example, if cluster health goes red, you might restore the red indexes from a snapshot.
    
2.  Migrating from one cluster to another
    
    For example, if you’re moving from a proof of concept to a production cluster, you might take a snapshot of the former and restore it on the latter.
    

You can take and restore snapshots using snapshot management in OpenSearch Dashboards.

If you need to automate snapshots creation, you can use a snapshot policy.

## Creating a repository[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#creating-a-repository)

Before you create an SM policy, you need to set up a repository for snapshots.

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Repositories**.
3.  Choose the  **Create Repository**  button.
4.  Enter the repository name, type, and location.
5.  (Optional) Select  **Advanced Settings**  and enter additional settings for this repository as a JSON object. Example:
    
    ```
     {
         "chunk_size": null,
         "compress": false,
         "max_restore_bytes_per_sec": "40m",
         "max_snapshot_bytes_per_sec": "40m",
         "readonly": false
     }
    
    ```
    
6.  Choose the  **Add**  button.

## Deleting a repository[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#deleting-a-repository)

To delete a snapshot repository configuration, select the repository from the  **Repositories**  list and then choose the  **Delete**  button.

## Creating an SM policy[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#creating-an-sm-policy)

Create an SM policy to set up automatic snapshots. An SM policy defines an automated snapshot creation schedule and an optional automated deletion schedule.

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Snapshot Policies**.
3.  Select the  **Create Policy**  button.
4.  In the  **Policy settings**  section:
    1.  Enter the policy name.
    2.  (Optional) Enter the policy description.
5.  In the  **Source and destination**  section:
    1.  Select or enter source indexes either as a list or as an index pattern.
    2.  Select a repository for snapshots. To  [create a new repository](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#creating-a-repository), select the  **Create**  button.
6.  In the  **Snapshot schedule**  section:
    1.  Select the desired snapshot frequency or enter a custom cron expression for snapshot frequency.
    2.  Select the start time and time zone.
7.  In the  **Retention period**  section:
    1.  Choose to retain all snapshots or specify retention conditions (the maximum age of retained snapshots).
    2.  (Optional) In  **Additional settings**, select the minimum and maximum number of retained snapshots, deletion frequency, and deletion start time.
8.  In the  **Notifications**  section, select the snapshot activities you want to be notified about.
9.  (Optional) In the  **Advanced settings**  section, select the desired options:
    -   **Include cluster state in snapshots**
    -   **Ignore unavailable indices**
    -   **Allow partial snapshots**
10.  Select the  **Create**  button.

## View, edit, or delete an SM policy[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#view-edit-or-delete-an-sm-policy)

You can view, edit, or delete an SM policy on the policy details page.

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Snapshot Policies**.
3.  Click on the  **Policy name**  of the policy you want to view, edit, or delete.  
    The policy settings, snapshot schedule, snapshot retention period, notifications, and last creation and deletion are displayed in the policy details page.  
    If a snapshot creation or deletion fails, you can view information about the failure in the  **Last Creation/Deletion**  section. To view the failure message, click on the  **cause**  in the  **Info**  column.
4.  To edit or delete the SM policy, select the  **Edit**  or  **Delete**  button.

## Enable, disable, or delete SM policies[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#enable-disable-or-delete-sm-policies)

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Snapshot Policies**.
3.  Select one or more policies in the list.
4.  To enable or disable selected SM policies, select the  **Enable**  or  **Disable**  button. To delete selected SM policies, in the  **Actions**  list, select the  **Delete**  option.

## View snapshots[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#view-snapshots)

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Snapshots**. All automatically or manually taken snapshots appear in the list.
3.  To view a snapshot, click on its  **Name**.

## Take a snapshot[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#take-a-snapshot)

Use the steps below to take a snapshot manually:

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Snapshots**.
3.  Select the  **Take snapshot**  button.
4.  Enter the snapshot name.
5.  Select or enter source indexes either as a list or as an index pattern.
6.  Select a repository for the snapshot.
7.  (Optional) In the  **Advanced options**  section, select the desired options:
    -   **Include cluster state in snapshots**
    -   **Ignore unavailable indices**
    -   **Allow partial snapshots**
8.  Choose the  **Add**  button.

## Deleting a snapshot[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#deleting-a-snapshot)

The  **Delete**  button  [deletes](https://opensearch.org/docs/latest/api-reference/snapshots/delete-snapshot/)  a snapshot from a repository.

1.  To view a list of your repositories, choose  **Repositories**  under the  **Snapshot Management**  section.
2.  To view a list of your snapshots, choose  **Snapshots**  under the  **Snapshot Management**  section.

## Restoring a snapshot[](https://opensearch.org/docs/latest/dashboards/sm-dashboards/#restoring-a-snapshot)

1.  On the top menu bar, go to  **OpenSearch Plugins > Snapshot Management**.
2.  In the left panel, under  **Snapshot Management**, select  **Snapshots**. The  **Snapshots**  tab is selected by default.
3.  Select the checkbox next to the snapshot you want to restore, as shown in the following image:  ![Snapshots]({{site.baseurl}}/images/snapshot-management/restore-snapshot-main.png)
    
    You can only restore snapshots with the status of  `Success`  or  `Partial`. The status of the snapshot is displayed in the  **Snapshot status**  column.
    
4.  In the  **Restore snapshot**  flyout, select the options for restoring the snapshot.
    
    The  **Restore snapshot**  flyout lists the snapshot name and status. To view the list of indexes in the snapshot, select the number under  **Indices**  (for example,  `27`  in the following image). This number represents the number of indexes in the snapshot.
    
    ![Restore Snapshot]({{site.baseurl}}/images/snapshot-management/restore-snapshot.png)
    
    For more information about the options in the  **Restore snapshot**  flyout, see  [Restore snapshots](https://opensearch.org/docs/latest/opensearch/snapshots/snapshot-restore#restore-snapshots).
    
    **Ignoring missing indexes**
    
    If you specify which indexes you want to restore from the snapshot and select the  **Ignore unavailable indices**  option, the restore operation ignores the indexes that are missing from the snapshot. For example, if you want to restore the  `log1`  and  `log2`  indexes, but  `log2`  is not in the snapshot,  `log1`  is restored and  `log2`  is ignored. If you don’t select  **Ignore unavailable indices**, the entire restore operation fails if an index to be restored is missing from a snapshot.
    
    **Custom index settings**
    
    You can choose to customize some settings for the indexes restored from a snapshot:  
     • Select the  **Customize index settings**  checkbox to provide new values for the specified index settings. All newly restored indexes will use these values instead of the ones in the snapshot.  
     • Select the  **Ignore index settings**  checkbox to specify the settings in the snapshot to ignore. All newly restored indexes will use the cluster defaults for these settings.
    
    The examples in the following image set  `index.number_of_replicas`  to  `0`,  `index.auto_expand_replicas`  to  `true`, and  `index.refresh_interval`  and  `index.max_script_fields`  to the cluster default values for all newly restored indexes.
    
    ![Custom settings]({{site.baseurl}}/images/snapshot-management/restore-snapshot-custom.png)
    
    For more information about index settings, see  [Index settings](https://opensearch.org/docs/latest/api-reference/index-apis/create-index/#index-settings).
    
    For a list of settings that you cannot change or ignore, see  [Restore snapshots](https://opensearch.org/docs/latest/opensearch/snapshots/snapshot-restore#restore-snapshots).
    
    After choosing the options, select the  **Restore snapshot**  button.
    
5.  (Optional) To monitor the restore progress, select  **View restore activities**  in the confirmation dialog. You can also monitor the restore progress at any time by selecting the  **Restore activities in progress**  tab, as shown in the following image.
    
    ![Restore Activities]({{site.baseurl}}/images/snapshot-management/restore-snapshot-activities.png)
    
    You can view the percentage of the job that has been completed in the  **Status**  column. Once the snapshot restore is complete, the  **Status**  changes to  `Completed (100%)`.
    
    The  **Restore activities in progress**  panel is not persistent. It displays only the progress of the current restore operation. If multiple restore operations are running, the panel displays the most recent one.
    
    To view the status of each index being restored, select the link in the  **Indices being restored**  column (in the preceding image, the  `27 Indices`  link). The  **Indices being restored**  flyout (shown in the following image) displays each index and its restore status.
    
    ![Restore Indices]({{site.baseurl}}/images/snapshot-management/restore-snapshot-indices.png)
    

After the restore operation is complete, the restored indexes are listed in the  **Indices**  panel. To view the indexes, in the left panel, under  **Index Management**, choose  **Indices**.

![View Indices]({{site.baseurl}}/images/snapshot-management/restore-snapshot-indices-panel.png)