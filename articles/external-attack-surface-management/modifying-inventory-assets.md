---
title: Modify inventory assets 
description: This article outlines how to update assets with customized text labels to categorize and make use of inventory data.
ms.author: dandennis
author: dandennis
ms.service: defender-easm
ms.date: 3/1/2022
ms.topic: how-to
---

# Asset modification overview

This article outlines how to modify inventory assets. You can change the state of an asset, assign an external ID or apply labels to help provide context and use inventory data. Users can also remove assets from their inventory in bulk based on the method with which they were discovered; for instance, users can remove a seed from a discovery group and elect to remove any assets that were discovered through a connection to this seed. This article describes all modification options available in Defender EASM, and outlines how to update assets and track any updates with the Task Manager.

### Label assets

Labels help you organize your attack surface and apply business context in a customizable way. You can apply any text label to a subset of assets to group assets and make better use of your inventory. Customers commonly categorize assets that:

- Have recently come under your organization's ownership through a merger or acquisition.
- Require compliance monitoring.
- Are owned by a specific business unit in their organization.
- Are affected by a specific vulnerability that requires mitigation.
- Relate to a particular brand owned by the organization.
- Were added to your inventory within a specific time range.
  

Labels are free form text fields, so you can create a label for any use case that applies to your organization.

[![Screenshot that shows an inventory list view with a filtered Labels column.](media/labels-1a.png)](media/labels-1a.png#lightbox)


### Change the state of an asset 

Users can also change the state of an asset. States help categorize your inventory based on their role in your organization. Users can switch between the following states: 
- **Approved Inventory**:	A part of your owned attack surface; an item that you are directly responsible for.
- **Dependency**:	Infrastructure that is owned by a third party but is part of your attack surface because it directly supports the operation of your owned assets. For example, you might depend on an IT provider to host your web content. While the domain, hostname, and pages would be part of your “Approved Inventory,” you may wish to treat the IP Address running the host as a “Dependency.”
- **Monitor Only**:	An asset that is relevant to your attack surface but is neither directly controlled nor a technical dependency. For example, independent franchisees or assets belonging to related companies might be labeled as “Monitor Only” rather than “Approved Inventory” to separate the groups for reporting purposes.
- **Candidate**:	An asset that has some relationship to your organization's known seed assets but does not have a strong enough connection to immediately label it as “Approved Inventory.” These candidate assets must be manually reviewed to determine ownership.
- **Requires Investigation**:	A state similar to the “Candidate” states, but this value is applied to assets that require manual investigation to validate. This is determined based on our internally generated confidence scores that assess the strength of detected connections between assets. It does not indicate the infrastructure's exact relationship to the organization as much as it denotes that this asset has been flagged as requiring additional review to determine how it should be categorized.


### Apply an External ID 

Users can also apply an external ID to an asset. This is useful in situations when you employ multiple solutions for asset tracking, remediation activities or ownership monitoring; seeing any external IDs within Defender EASM helps you align this disparate asset information. External ID values can be numeric or alphanumeric and must be entered in text format. External IDs are also displayed within the Asset Details section. 


## How to modify assets 

You can modify assets from both the inventory list and asset details pages. You can make changes to a single asset from the asset details page. You can make changes to a single asset or multiple assets from the inventory list page. The following sections describe how to apply changes from the two inventory views depending on your use case.

### Inventory list page

You should modify assets from the inventory list page if you want to update numerous assets at once. You can refine your asset list based on filter parameters. This process helps you to identify assets that should be categorized with the label, external ID or state change that you want. To modify assets from this page:

1. On the leftmost pane of your Microsoft Defender External Attack Surface Management (Defender EASM) resource, select **Inventory**.

2. Apply filters to produce your intended results. In this example, we're looking for domains that expire within 30 days that require renewal. The applied label helps you more quickly access any expiring domains to simplify the remediation process. You can apply as many filters as necessary to obtain the specific results that are needed. For more information on filters, see [Inventory filters overview](inventory-filters.md).

   ![Screenshot that shows the inventory list view with the Add filter dropdown opened to display the query editor.](media/labels-2.png)

3. After your inventory list is filtered, select the dropdown by the checkbox next to the **Asset** table header. This dropdown gives you the option to select all results that match your query or the results on that specific page (up to 25). The **None** option clears all assets. You can also choose to select only specific results on the page by selecting the individual check marks next to each asset.

   ![Screenshot that shows the inventory list view with the bulk selection dropdown opened.](media/labels-14.png)

4. Select **Modify assets**.

5. On the **Modify Assets** pane that opens on the right side of your screen, you can quickly change the state of the selected assets. For this example, you create a new label. Select **Create a new label**.

6. Determine the label name and display text values. The label name can't be changed after you initially create the label, but the display text can be edited at a later time. The label name is used to query for the label in the product interface or via API, so edits are disabled to ensure these queries work properly. To edit a label name, you need to delete the original label and create a new one.

   Select a color for your new label and select **Add**. This action takes you back to the **Modify Assets** screen.

   ![Screenshot that shows the Add label pane that displays the configuration fields.](media/labels-4.png)

7. Apply your new label to the assets. Click inside the **Add labels** text box to view a full list of available labels. Or you can type inside the box to search by keyword. After you select the labels you want to apply, select **Update**.

   ![Screenshot that shows the Modify Asset pane with the newly created label applied.](media/labels-5.png)

8. Allow a few moments for the labels to be applied. After the process is finished, you see a "Completed" notification. The page automatically refreshes and displays your asset list with the labels visible. A banner at the top of the screen confirms that your labels were applied.

   [![Screenshot that shows the inventory list view with the selected assets now displaying the new label.](media/labels-6.png)](media/labels-6.png#lightbox)


### Asset details page

You can also modify a single asset from the asset details page. This option is ideal for situations when assets need to be thoroughly reviewed before a label or state change is applied.

1. On the leftmost pane of your Defender EASM resource, select **Inventory**.

2. Select the specific asset you want to modify to open the asset details page.

3. On this page, select **Modify asset**.

   ![Screenshot that shows the asset details page with the Modify asset button highlighted.](media/labels-7a.png)

4. Follow steps 5 to 7 in the "Inventory list page" section.

5. The asset details page refreshes and displays the newly applied label or state change. A banner indicates that the asset was successfully updated.


## Modify, remove, or delete labels

Users can remove a label from an asset by accessing the same **Modify asset** pane from either the inventory list or asset details view. From the inventory list view, you can select multiple assets at once and then add or remove the desired label in one action.

To modify the label itself or delete a label from the system:

1. On the leftmost pane of your Defender EASM resource, select **Labels (Preview)**.

   [![Screenshot that shows the Labels (Preview) page that enables label management.](media/labels-8a.png)](media/labels-8a.png#lightbox)

   This page displays all the labels within your Defender EASM inventory. Labels on this page might exist in the system but not be actively applied to any assets. You can also add new labels from this page.

2. To edit a label, select the pencil icon in the **Actions** column of the label you want to edit. A pane opens on the right side of your screen where you can modify the name or color of a label. Select **Update**.

3. To remove a label, select the trash can icon from the **Actions** column of the label you want to delete. Select **Remove Label**.

   ![Screenshot that shows the Confirm Remove option on the Labels management page.](media/labels-9a.png)

The **Labels** page automatically refreshes. The label is removed from the list and also removed from any assets that had the label applied. A banner confirms the removal.


## Task Manager and notifications

After a task is submitted, a notification confirms that the update is in progress. From any page in Azure, select the notification (bell) icon to see more information about recent tasks.

![Screenshot that shows the Task submitted notification.](media/labels-12.png)
![Screenshot that shows the Notifications pane that displays recent task status.](media/labels-13.png)

The Defender EASM system can take seconds to update a handful of assets or minutes to update thousands. You can use the Task Manager to check on the status of any modification tasks in progress. This section outlines how to access the Task Manager and use it to better understand the completion of submitted updates.

1. On the leftmost pane of your Defender EASM resource, select **Task Manager**.

   ![Screenshot that shows the Task Manager page with appropriate section in navigation pane highlighted.](media/labels-11a.png)

2. This page displays all your recent tasks and their status. Tasks are listed as **Completed**, **Failed**, or **In Progress**. A completion percentage and progress bar also appear. To see more details about a specific task, select the task name. A pane opens on the right side of your screen that provides more information.

3. Select **Refresh** to see the latest status of all items in the Task Manager.


## Filter for labels

After you label assets in your inventory, you can use inventory filters to retrieve a list of all assets with a specific label applied.

1. On the leftmost pane of your Defender EASM resource, select **Inventory**.

2. Select **Add filter**.

3. Select **Labels** from the **Filter** dropdown list. Select an operator and choose a label from the dropdown list of options. The following example shows how to search for a single label. You can use the **In** operator to search for multiple labels. For more information on filters, see the [inventory filters overview](inventory-filters.md).

   ![Screenshot that shows the query editor used to apply filters, displaying the Labels filter with possible label values in a dropdown list.](media/labels-10.png)

4. Select **Apply**. The inventory list page reloads and displays all assets that match your criteria.



## Asset chain-based management 

In some instances, you may wish to remove multiple assets at once based on the means with which they were discovered. For example, you may determine that a particular seed within a discovery group has pulled in assets that are not relevant to your organization, or you may need to remove assets that relate to a subsidiary that is no longer under your purview. For this reason, Defender EASM offers the ability to remove the source entity and any assets "downstream" in the discovery chain. You can delete linked assets with the following three methods: 

- **Seed-based management:** users can delete a seed that was previously included in a discovery group, removing all assets that were introduced to inventory through an observed connection to the specified seed. This method is useful when you can determine that a specific manually inputted seed resulted in undesired assets being added to inventory. 
- **Discovery chain management**: users can identify an asset within a discovery chain and delete it, simultaneously removing any assets discovered by that entity. Discovery is a recursive process; it scans seeds to identify new assets directly associated to these designated seeds, then continues to scan the newly discovered entities to unveil more connections. This deletion approach is useful when your discovery group is properly configured, but you need to remove a newly discovered asset and any asset(s) brought into inventory by association to that entity. Consider your discovery group settings and designated seeds to be the "top" of your discovery chain; this deletion approach allows you to remove assets from the middle.
- **Discovery group management:** users can remove entire discovery group(s) and all assets that were introduced to inventory through this discovery group. This is useful when an entire discovery group is no longer applicable to your organization. For instance, you may have a discovery group that specifically searches for assets related to a subsidiary. If this subsidiary is no longer relevant to your organization, you can leverage asset chain-based management to delete all assets brought into inventory through that discovery group.

 You can still view removed assets in Defender EASM; simply filter your inventory list for assets in the "Archived" state. 


### Seed-based deletion 

You may decide that one of your initially designated discovery seeds should no longer be included in a discovery group.  The seed may no longer be relevant to your organization, or it might be bringing in more false positives than legitimate owned assets. In this situation, you can remove the seed from your Discovery Group to prevent it from being used in future discovery runs while simultaneously removing any assets that have been brought to inventory through the designated seed in the past. 

To perform a bulk removal based on a seed, route to the appropriate Discovery Group details page and click "Edit discovery group."  Follow the prompts to reach the Seeds page, and remove the problematic seed from the list. When you select "Review + Update", you will see a warning that indicates that all assets discovered through the designated seed will be removed as well. Select "Update" or "Update & Run" to complete the deletion. 

![Screenshot that shows the Edit Discovery Group page with a warning indicating the removal of a seed and any assets discovered through that seed.](media/chain-1.png)



### Discovery chain-based deletion 

In the following example, imagine that you've discovered an insecure login form on your Attack Surface Summary dashboard. Your investigation routes you to a host that does not appear to be owned by your organization. You view the asset details page for more information; upon reviewing the Discovery chain, you learn that the host was brought into inventory because the corresponding domain was registered using an employee's corporate email address that was also used to register approved business entities. 

![Screenshot that shows the Asset Details page with the Discovery Chain section highlighted.](media/chain-2.png)

In this situation, the initial discovery seed (the corporate domain) is still legitimate so we need to instead remove a problematic asset from the discovery chain. While we could perform the chain deletion from the contact email, we'll instead elect to remove everything associated to the personal domain registered to this employee so that Defender EASM will alert us of any other domains registered to that email address in the future. From the discovery chain, select this personal domain to view the asset details page. From this view, select "Remove from discovery chain" to remove the asset from your inventory, as well as all assets brought into inventory due to an observed connection to the personal domain. You will be asked to confirm the removal of the asset and all downstream assets and will be presented with a summarized list of the other assets that will be removed with this action. Select "Remove discovery chain" to confirm the bulk removal. 

![Screenshot that shows the box that prompts users to confirm the removal of the current asset and all downstream assets, with a summary of the other assets that will be removed with this action.](media/chain-3.png)


### Discovery group deletion 

You may need to delete and entire discovery group and all the assets discovered through the group.  For instance, your company may have sold a subsidiary that no longer needs to be monitored. Users can delete discovery groups from the Discovery management page. To remove a discovery group and all related assets, simply select the trash bin icon next to the appropriate group in the list. You will receive a warning that lists a summary of the assets that will be removed with this action. To confirm the deletion of the discovery group; and all related assets, select "Remove discovery group." 

![Screenshot that shows the Discovery management page, with the warning box that appears after electing to delete a group highlighted.](media/chain-4.png)



  
## Next steps

- [Inventory filters overview](inventory-filters.md)
- [Understand inventory assets](understanding-inventory-assets.md)
- [Understand asset details](understanding-asset-details.md)
