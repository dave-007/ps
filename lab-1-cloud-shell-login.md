## Lab Name: Azure Cloud Shell First Login

### Task 1: In your browser, login to your Azure account at **https://portal.azure.com**.

Test 1: If successful, you will see your Azure Portal home page.

### Task 2: Click the Cloud Shell icon in the upper right of your Azure Portal home page to open your Azure Cloud Shell, and configure your cloud drive storage.

![Cloud Shell Icon](https://i.imgur.com/nLx6dsO.png)

If this is your first time in the shell you will be prompted to choose Bash or PowerShell, **choose PowerShell**. You are then prompted create your cloud drive storage. Rather than accepting the defaults by clicking the **Create storage** button, lick the **Show advanced settings** link.

![Prompt to create Azure file share](https://i.imgur.com/7EdXAsL.png)

Choose your desired **subscription**, and a nearby **region** to host your cloud shell storage. For your new resource group, storage account, and file share fields, ensure the **Create new** radio button is selected, and enter desired values each field. (Alternately, you may choose to use existing resources if previously created.)

Click the **Create storage** button to proceed.

If any provided values are invalid, an error is displayed that describes acceptable characters for each field. For example, ensure your *storage account name is unique and composed of lowercase letters and numbers*. Once you have made your corrections, click **Create storage** to continue.

Note: Naming things in Azure involves learning what rules apply to which types of resources. Lowercase letters and numbers work for most situations. Review these docs pages for more information:
* [Naming rules and restrictions for Azure resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/resource-name-rules)
*  [Recommended naming and tagging conventions](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/naming-and-tagging) 

Test 1: If successful, cloud shell will display.

![Cloud shell](https://i.imgur.com/t27N5kH.png)

#### Task 3: Verify your Cloud Shell resources with basic PowerShell commands.

From your Cloud Shell, type `Get-AzResourceGroup` to list the resource groups in your subscription, and note the name of the resource group you just created. The resource group name **rgCloudShell** will be used in this example.

Test 2: Type `Get-AzStorageAccount -ResourceGroupName rgCloudShell`, replacing **rgCloudShell** with your resource group name, to view the storage account you just created.

```ps

PS Azure:\> Get-AzStorageAccount -ResourceGroupName rgCloudShell

StorageAccountName ResourceGroupName PrimaryLocation SkuName      Kind      AccessTier CreationTime         ProvisioningState EnableHttpsTrafficOnly LargeFileShares
------------------ ----------------- --------------- -------      ----      ---------- ------------         ----------------- ---------------------- ---------------
storcloudshell123   rgCloudShell      eastus          Standard_LRS StorageV2 Hot        3/6/2020 11:21:39 AM Succeeded         True

Azure:/
PS Azure:\>
```

Test 3: Type ``Get-AzRMStorageShare -ResourceGroupName rgCloudShell -StorageAccount storcloudshell123 `,replacing **rgCloudShell** with your resource group name and **storcloudshell123** with your storage account name, to view the file share you just created.

```ps

PS Azure:\> Get-AzRmStorageShare -ResourceGroupName rgCloudshell -StorageAccountName storcloudshell123

Name         StorageAccountName ResourceGroupName Etag                QuotaGiB LastModifiedTime
----         ------------------ ----------------- ----                -------- ----------------
fscloudshell storcloudshelldc   rgCloudshell      "0x8D7C1C0F2496956" 6        2020-03-06 11:24:33Z
```