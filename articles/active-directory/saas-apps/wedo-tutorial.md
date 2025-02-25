---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with WEDO | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and WEDO.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 11/21/2022
ms.author: jeedes
---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with WEDO

In this tutorial, you'll learn how to integrate WEDO with Azure Active Directory (Azure AD). When you integrate WEDO with Azure AD, you can:

* Control in Azure AD who has access to WEDO.
* Enable your users to be automatically signed-in to WEDO with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* WEDO single sign-on (SSO) enabled subscription. Please contact [WEDO Client support team](mailto:info@wedo.swiss) to get a SSO subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* WEDO supports **SP and IDP** initiated SSO.
* WEDO supports [Automated user provisioning](wedo-provisioning-tutorial.md).

## Add WEDO from the gallery

To configure the integration of WEDO into Azure AD, you need to add WEDO from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **WEDO** in the search box.
1. Select **WEDO** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, as well as walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Azure AD SSO for WEDO

Configure and test Azure AD SSO with WEDO using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in WEDO.

To configure and test Azure AD SSO with WEDO, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure WEDO SSO](#configure-wedo-sso)** - to configure the single sign-on settings on application side.
    1. **[Create WEDO test user](#create-wedo-test-user)** - to have a counterpart of B.Simon in WEDO that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **WEDO** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.wedo.swiss/sp/acs`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.wedo.swiss/sp/acs`

1. Click **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.wedo.swiss/`

	> [!NOTE]
	> These values are not real. Update these values with the actual Identifier, Reply URL and Sign-on URL. Contact [WEDO Client support team](mailto:info@wedo.swiss) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

1. WEDO application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	| Name | Source Attribute|
	| ------------ | --------- |
	| email | user.email |
	| firstName | user.firstName |
    | lastName | user.lasttName |
	| userName | user.userName |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up WEDO** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to WEDO.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **WEDO**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.
1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.
1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you're expecting any role value in the SAML assertion, in the **Select Role** dialog, select the appropriate role for the user from the list and then click the **Select** button at the bottom of the screen.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure WEDO SSO

Follow these steps to enable Azure AD SSO in WEDO.

1. Log in [WEDO](https://login.wedo.swiss/). You need to have **administrator role**.
1. In the Profile settings, select the menu **Authentication** in the section **Network settings**.
1. On the **SAML Authentication** page, perform the following steps:

   ![SAML Authentication link](media/wedo-tutorial/network-security-authentification.png)

   a. Enable **SAML Authentication**.

   b. Select the **Identity Provider metadata (XML)** tab.

   c. Open the downloaded **Federation Metadata XML** from Azure portal into Notepad and copy the content of metadata XML and paste it into **X.509 Certificate** textbox.

   d. Click **Save**.

### Create WEDO test user

In this section, you'll create a test user in WEDO called Bob Simon. Information must matches from **Create an Azure AD test user**.

1. From the Profile setting in WEDO, select **Users** from **Network settings** section.
1. Click **Add user**.
1. In the Add user pop-up, fill the user's information

    a. First name `B`.

    b. Last name `Simon`.

    c. Enter the email `username@companydomain.extension`. For example, `B.Simon@contoso.com`. It is mandatory to have email with the same domain as your company short name.

    d. User type `User`.

    e. Click **Create user**.

    f. In the **Select teams** page, click **Save**.

    g.  In the **Invite user** page, click **Yes**.

1. Validate the user using the link you received by email

> [!NOTE]
> If you want to create a fake user (email above does not exist in your network), contact [our support](mailto:info@wedo.swiss) to validate the user*.

> [!NOTE]
> WEDO also supports automatic user provisioning, you can find more details [here](./wedo-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO

In this section, you test your Azure AD single sign-on configuration with the following options. 

#### SP initiated:

* Click **Test this application** in Azure portal. This will redirect to WEDO Sign on URL where you can initiate the login flow.  

* Go to WEDO Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Click **Test this application** in Azure portal and you should be automatically signed in to the WEDO for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you click the WEDO tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the WEDO for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](../user-help/my-apps-portal-end-user-access.md).

## Next steps

Once you configure WEDO you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
