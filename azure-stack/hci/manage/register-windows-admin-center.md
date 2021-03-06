---
title: Register Windows Admin Center with Azure
description: How to register your Windows Admin Center gateway with Azure.
author: khdownie
ms.author: v-kedow
ms.topic: how-to
ms.date: 03/04/2021
---

# Register Windows Admin Center with Azure

> Applies to Azure Stack HCI v20H2; Windows Server 2019

To use Azure services with Windows Admin Center, you must first [install Windows Admin Center](/windows-server/manage/windows-admin-center/deploy/install) on a management PC and register your Windows Admin Center gateway. This is a prerequisite for [registering a cluster](../deploy/register-with-azure.md) with Azure.

   > [!IMPORTANT]
   > Register Windows Admin Center on the same management PC you plan to use to register your cluster(s), using the same Azure Active Directory (tenant) ID and Application ID.

## Complete the registration process

1. Launch Windows Admin Center and click the **Settings** gear icon in the upper right, which will take you to your Account page. Then, from the **Gateway** menu at the left, select **Azure**, and then click **Register**.

   :::image type="content" source="media/register-wac/register-wac.png" alt-text="Select Settings > Gateway > Azure, then click Register" lightbox="media/register-wac/register-wac.png":::

2. You'll be provided with a unique code. Click the **Copy** button to the right of the code. Click **Enter the code**, which will open up another browser window into which you can paste the code displayed on your app or device.

   :::image type="content" source="media/register-wac/enter-code.png" alt-text="Copy the unique code, click enter the code, and paste it into the dialog box" lightbox="media/register-wac/enter-code.png":::

3. After pasting in the code, you'll be notified that you're about to be signed in to Windows Admin Center on a remote device or service. Enter your email or phone number. If your device is managed, you will be taken to your organization's sign-in page for authentication. Follow the instructions and enter the appropriate credentials.

   :::image type="content" source="media/register-wac/sign-in.png" alt-text="Sign in to Windows Admin Center using your email or phone number" lightbox="media/register-wac/sign-in.png":::

   You should see the following message: "You have signed in to the Windows Admin Center application on your device." Close the browser window to return to the original registration page.

4. Connect to Azure Active Directory by supplying your Azure Active Directory (tenant) ID and application ID. If you already have an Azure tenant ID and you've followed the preceding steps, the tenant ID field may be pre-populated and may contain multiple options. Select the correct tenant ID. If your Azure AD administrator has provided you with an application ID, click **Use existing**, and an empty field will appear for you to enter the ID provided by your admin. After entering your ID, Windows Admin Center will confirm that an account with that ID is found. If you have an existing ID but don't know what it is, follow [these steps](/azure/active-directory/develop/howto-create-service-principal-portal#get-values-for-signing-in) to retrieve it. If your organization didn't provide you with an existing ID, leave **Azure Active Directory application** set to **Create New**.

   :::image type="content" source="media/register-wac/connect-to-aad.png" alt-text="Connect to Azure Active Directory by supplying your existing Azure Active Directory (tenant) ID or creating a new one" lightbox="media/register-wac/connect-to-aad.png":::

5. Click the **Connect** button to connect to Azure. If you are an Azure AD admin or if you used an existing application ID, you should see a confirmation that you are now connected to Azure AD. If not, you may see a message that you need admin approval. If this is the case, select **Return to the application without granting consent**, and contact your Azure AD admin to grant permissions to the new application ID that was created upon registration by following the instructions in step 6.

6. If you are an Azure AD admin, grant permissions in Azure by navigating to **Azure Active Directory**, then **App registrations**. Select the app identity named after the gateway you're registering, and navigate to **API permissions**. Under **Grant consent**, select **Grant admin consent**.

7. Close the window and sign into Windows Admin Center with your Azure account.

## Next steps

You are now ready to:

- [Connect Azure Stack HCI to Azure](../deploy/register-with-azure.md)
- [Use Azure Stack HCI with Windows Admin Center](../get-started.md)
- [Connect to Azure hybrid services](/windows-server/manage/windows-admin-center/azure/)