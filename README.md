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

## Cloud Runtime Compatibility

### Import Flow-service
9. Download **executeActionOnCRT.zip** file from the **Releases** section of this GitHub repository.
10. Select **Integrations** tab in webMethods.io Integration project.
11. Select **Flow Services** tab in the left-hand side navigation.
12. Click **Import** button.
13. Choose **executeActionOnCRT.zip** file and click **Open** button.
14. Click **Submit** button.

### Import Workflow
15. Download **Execute_Action_on_CRT.zip** files from the **Releases** section of this GitHub repository.
16. Select the **Workflows** tab in the left-hand side navigation in webMethods.io Integration project.
17. Click **Import** button.
18. Choose **Execute_Action_on_CRT.zip** file and click **Open** button.
19. Click **Import** button.

### Configure API
20. Select the **APIs** tab.
21. Click on **Create API** button.
22. Select **Create from Scratch / Design new API** and click **Next** button.
    * Provide a **Name**. Example: **WxPCACloudRuntimeClient**.
    * Provide a **Version**. Example: **1.0**.
23. Click **Save** button.
24. Click **Add resource** button.
    * Provide **Path** value as **/execute**.
    * Select **HTTP Method** as **POST**.
    * In **Select Workflow/Flow service** dropdown, choose **Execute Action on CRT** workflow.
    * Click **Done** button and then click **Save** button.

proceed to [this section](https://github.com/IBM/WxPCATargetRuntimeClient/tree/main?tab=readme-ov-file#get-url-to-configure-target-runtime-in-wxpackagecompatibilityanalyzer) to get URL to configure target runtime in WxPackageCompatibilityAnalyzer.

## Edge Runtime Compatibility

### Import Flow-service
9. Download **executeActionOnERT.zip** file from the **Releases** section of this GitHub repository.
10. Select **Integrations** tab in webMethods.io Integration project.
11. Select **Flow Services** tab in the left-hand side navigation.
12. Click **Import** button.
13. Choose **executeActionOnERT.zip** file and click **Open** button.

### Sync the Flow-service to Edge Runtime
14. Click on **executeActionOnERT** flow service to open it.
15. Click on **Expand All** button below flow service title.
16. In **flow step 2**, click on **Cloud Runtime** and select your edge runtime from the **Search Runtime** dropdown.
17. Click on **Sync** button (located next to "Search Runtime" dropdown) to synchronize with the selected edge runtime.
18. On **Success** message, click on **Save** button.
19. **Exit** from the executeActionOnERT flow service.

### Configure API
20. Select the **APIs** tab.
21. Click on **Create API** button.
22. Select **Create from Scratch / Design new API** and click **Next** button.
    * Provide a **Name**. Example: **WxPCAEdgeRuntimeClient**.
    * Provide a **Version**. Example: **1.0**.
23. Click **Save** button.
24. Click **Add resource** button.
    * Provide **Path** value as **/execute**.
    * Select **HTTP Method** as **POST**.
    * In **Select Workflow/Flow service** dropdown, choose **executeActionOnERT** flow service.
    * Click **Done** button and then click **Save** button.


## Get URL to Configure Target Runtime in WxPackageCompatibilityAnalyzer
1. Login to the webMethods.io Integration tenant.
2. In the **Projects** tab, open the project created earlier using the steps above.
3. Select the **APIs** tab.
4. Click on the API to open it.
5. In the **Basic Info** section of the API, click the **Copy** icon for **Public URL** corresponding to **API Endpoint**. An example copied URL will be "https://somewmiotenant.int-aws-de.webmethods.io/integration/restv2/development/flec1bd19aa493d26689ccc0/WxPCACloudRuntimeClient".
