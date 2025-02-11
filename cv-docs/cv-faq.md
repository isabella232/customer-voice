---
title: "Frequently asked questions | MicrosoftDocs"
description: "Use this topic to know about the frequently asked questions and their answers in Dynamics 365 Customer Voice."
ms.date: 03/08/2022
ms.topic: article
author: sbmjais
ms.author: shjais
manager: shujoshi
---

# Dynamics 365 Customer Voice FAQ

We've compiled a list of frequently asked questions and provided brief answers to help you get to your information quickly.

## I created a guest user in Azure Active Directory, but the user is unable to access Dynamics 365 Customer Voice.

Guest user access is not supported in Dynamics 365 Customer Voice. You must create a new user in your tenant and then provide access to the new user.

## How is the owner of a survey response determined?

A response owner is determined by the following logic:

- For responses to a survey invitation, the invitation owner is set as the response owner.
- If the survey invitation owner doesn't have sufficient privileges to own responses, or if the response is anonymous, the survey owner is set as the response owner.
- If the account of a survey owner has been disabled or the survey owner is unable to access the application due to licensing issues, the application user is set as the response owner.

## I deleted data from Microsoft Dataverse but it is visible in reports.

It is recommended not to delete data directly from Microsoft Dataverse. If you delete any data directly from Microsoft Dataverse, it is not synchronized with Customer Voice services. If you want to delete any data, you must delete using the Dynamics 365 Customer Voice interface.

## Why does the application user require the System Administrator role?

The application user requires the System Administrator role to associate survey invites and responses to any of the entities, including custom entities.

## What happens if the project owner leaves the organization?

If the project owner leaves the organization, the project will be deleted once the user is removed from the organization. If the project was shared by the user before leaving the organization, the existing user, with whom the project is shared, must create a [copy of the project](manage-projects.md#copy-a-project) and use the copied project.

## What languages are supported for sentiment analysis?

Dynamics 365 Customer Voice supports the following languages for sentiment analysis:

|     Language                 |     Language code    |
|------------------------------|------------------------|
|     Chinese                  |     zh                 |
|     Chinese-Simplified       |     zh-hans            |
|     Chinese-Traditional      |     zh-hant            |
|     Dutch                    |     nl                 |
|     English                  |     en                 |
|     French                   |     fr                 |
|     German                   |     de                 |
|     Hindi                    |     hi                 |
|     Italian                  |     it                 |
|     Japanese                 |     ja                 |
|     Korean                   |     ko                 |
|     Norwegian (Bokmål)       |     no                 |
|     Portuguese (Brazil)      |     pt-BR              |
|     Portuguese (Portugal)    |     pt-PT              |
|     Portuguese               |     pt                 |
|     Spanish                  |     es                 |
|     Turkish                  |     tr                 |
|||

Survey responses received in languages other than the ones specified above are considered as English and sent to the cognitive services for further processing. In this case, the accuracy would be impacted.

## How can I change the ownership of satisfaction metrics and alerts from owner to a team?

### Assign the satisfaction metric record from owner to a team

1. Sign in to [Power Apps](https://make.powerapps.com/) with a user that has access to Dynamics 365 records.

2. Select **Settings** > **Advanced settings**.

    :::image type="content" source="media/advanced-settings-pa.png" alt-text="Go to advanced settings in Power Apps":::

3. Select **Advanced Find** on the command bar at the top.

    :::image type="content" source="media/advanced-find.png" alt-text="Go to advanced find":::

4. In the **Look for** list, select **Customer Voice satisfaction metric**.

5. In the **Select** list, select **Project**.

6. Select **Enter value**, then browser and select the name of the project.

    :::image type="content" source="media/advanced-find-window-sm.png" alt-text="Advanced find filter values for satisfaction metrics":::

7. Select **Results**. A list of all satisfaction metrics associated to the project is displayed.

8. Select the records whose ownership needs to be changed, and then select **Assign Customer Voice Satisfaction metric**.
 
    :::image type="content" source="media/advanced-find-results-sm.png" alt-text="Advanced find result for satisfaction metrics":::

9. In the **Assign Customer Voice satisfaction metric** window, select the **Assign to** field to change its value to **User or team**.

10. In the **User or team** field, browse and select the team to which ownership needs to be transferred.

    :::image type="content" source="media/assign-window-sm.png" alt-text="Assign the selected satisfaction metrics to a team":::

    > [!NOTE]   
    > To know how to find a team, see [How to find a team?](#how-to-find-a-team).

11. Select **Assign**.

### Assign the alert record from owner to a team

1. Sign in to [Power Apps](https://make.powerapps.com/) with a user that has access to Dynamics 365 records.

2. Select **Settings** > **Advanced settings**.

    :::image type="content" source="media/advanced-settings-pa.png" alt-text="Go to advanced settings in Power Apps":::

3. Select **Advanced Find** on the command bar at the top.

    :::image type="content" source="media/advanced-find.png" alt-text="Go to advanced find":::

4. In the **Look for** list, select **Customer Voice alert**.

5. In the **Select** list, select **Project**.

6. Select **Enter value**, then browser and select the name of the project.

7. Add the **Owner** column.

    :::image type="content" source="media/advanced-find-window-alert.png" alt-text="Advanced find filter values for alerts":::

8. Select **Results**. A list of all alerts associated to the project is displayed.

9. Select the records whose ownership needs to be changed, and then select **Assign Customer Voice alert**.

    :::image type="content" source="media/advanced-find-results-alert.png" alt-text="Advanced find result for alerts":::

10. In the **Assign to Team or User** window, select the **Assign to** field to change its value to **User or team**.

11. In the **User or team** field, browse and select the team to which ownership needs to be transferred.

    :::image type="content" source="media/assign-window-alert.png" alt-text="Assign the selected alerts to a team":::

12. Select **Assign**.
 
### How to find a team?

1. In the **Assign to Team or User** window, select the **Assign to** field to change its value to **User or team**.

2. Hover over the **User or team** field, and select the **Select a value** icon.
 
    :::image type="content" source="media/find-team.png" alt-text="Find a team":::

3. In the list, select **Look Up More Records**.

    :::image type="content" source="media/find-team-lookup.png" alt-text="Lookup more records":::

4. In the **Lookup Record** window, enter or select the following values:
    - **Look for**: Team
    - **Look in**: All AAD office Group Teams
    - **Search**: Name of the team.
    - Select the **Search** icon next to this field.

    :::image type="content" source="media/find-team-lookup-record-window.png" alt-text="Lookup Record window":::

5. From the search results, select a team, and then select **Add**.

## I deleted the old surveys and survey responses, and want to update values in the satisfaction metrics report accordingly.

This is an unsupported scenario. Deleting old surveys and survey responses will not update values in the satisfaction metrics report.

## I want to delete multiple responses from the Dynamics 365 Customer Voice interface.

Deleting multiple responses from the Dynamics 365 Customer Voice interface is not supported.

## I restored Microsoft Dataverse and want Dynamics 365 Customer Voice and survey responses to work with it.

This is an unsupported scenario.

## How can I share new feature requirements or ideas?

You can share your new feature requirements or ideas on the [Customer Voice Ideas](https://aka.ms/customervoiceideas) page.


[!INCLUDE[footer-include](includes/footer-banner.md)]
