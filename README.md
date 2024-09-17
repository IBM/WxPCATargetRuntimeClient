# WxPCATargetRuntimeClient
WxPCATargetRuntimeClient is webMethods Integration package for webMethods.io Integration to support [WxPackageCompatibilityAnalyzer](https://github.com/IBM/WxPackageCompatibilityAnalyzer.git) to analyze package dependencies against webMethods.io Integration Cloud runtime and webMethods Edge Runtime.

**Pre-requisites**
* webMethods.io Integration tenant
* GitHub account

## Installation & Configuration

### Add WxPCATargetRuntimeClient package
1. Login to the webMethods.io Integration tenant.
2. Select the **Projects** tab.
3. Create a new project or select an existing project.
4. Select the **Packages** tab in the project.
5. Click on **Add package** button and select **GIT**.
   * Provide **Git URL** as https://github.com/IBM/WxPCATargetRuntimeClient.git.
   * Select the **Source Control** or add new Git account if doesn't exist already.
6. Click **Next** button.
7. Select **Git branch/tag** as **main** branch.
8. Click the **Pull** button.

Now you can see **WxPCATargetRuntimeClient** package in the packages list.

### Import Flow-services
9. Download **executeAction.zip** file from the **Releases** section of this GitHub repository.
10. Select **Integrations** tab in webMethods.io Integration project.
11. Select **Flow Services** tab in the left-hand side navigation.
12. Click **Import** button.
13. Choose **executeAction.zip** file and click **Open** button.
14. Click **Submit** button.

### Import Workflows
15. Download **Execute_Action.zip** files from the **Releases** section of this GitHub repository.
16. Select the **Workflows** tab in the left-hand side navigation in webMethods.io Integration project.
17. Click **Import** button.
18. Choose **Execute_Action.zip** file and click **Open** button.
19. Click **Import** button.

### Configure API
20. Select the **APIs** tab.
21. Click on **Create API** button.
22. Select **Create from Scratch / Design new API** and click **Next** button.
    * Provide a **Name**. Example: **WxPCATargetRuntimeClient**.
    * Provide a **Version**. Example: **1.0**.
23. Click **Save** button.
24. Click **Add resource** button.
    * Provide **Path** value as **/execute**.
    * Select **HTTP Method** as **POST**.
    * In **Select Workflow/Flow service** dropdown, choose **Execute Action** workflow.
    * Click **Done** button and then click **Save** button.

## Cloud Runtime Compatibility
For Cloud Runtime, no additional changes required in the workflow or flowservice imported. You can proceed to [this section](https://github.com/IBM/WxPCATargetRuntimeClient/tree/main?tab=readme-ov-file#get-url-to-configure-target-runtime-in-wxpackagecompatibilityanalyzer).

## Edge Runtime Compatibility
For Edge Runtime, you need to sync **executeAction** flow service to your **Edge Runtime** and select it in the **Execute Action** workflow.

#### Sync the flow-service to Edge Runtime
25. Select **Integrations** tab in webMethods.io Integration project.
26. Select the **Flow Services** tab in the left-hand side navigation.
27. Click on **executeAction** flowservice to open it.
28. Select your edge runtime from the **Search Runtime** dropdown available on the Flow Editor menu bar.
29. Click on **Sync** button (located next to "Search Runtime" dropdown) to synchronize all assets in the project with the selected edge runtime.
30. On **Success** message exit from the flow service.

#### Select the Edge Runtime in workflow
31. Select **Integrations** tab in webMethods.io Integration project.
32. Select the **Workflows** tab in the left-hand side navigation.
33. Open the **Execute Action** workflow in **Edit** mode.
34. Hover over **Invoke executeAction Flowservice** action and click on **Settings** icon.
35. Under **Select Integration Runtime** dropdown, select your Edge Runtime against which you want to check the compatibility.
36. Click **Next** button.
37. Click **Next** button.
38. On **Test this action** page, make sure **"The runtime Your_Runtime_Name is up to date"** message is displayed in the left side of "Sync" and "Test" button. If not,
    * Click on **Sync** button.
    * On "Successfully synced" message, click **Close** button.
31. Click **Test** button.
32. Click **Done** button after output displayed successfuly.
33. Click on **Save** button at the top-right corner to save the workflow.

## Get URL to Configure Target Runtime in WxPackageCompatibilityAnalyzer
1. Login to the webMethods.io Integration tenant.
2. In the **Projects** tab, open the project created earlier using the steps above.
3. Select the **APIs** tab.
4. Click on the API to open it.
5. In the **Basic Info** section of the API, click the **Copy** icon for **Public URL** corresponding to **API Endpoint**. An example copied URL will be "https://somewmiotenant.int-aws-de.webmethods.io/integration/restv2/development/flec1bd19aa493d26689ccc0/WxPCATargetRuntimeClient".
