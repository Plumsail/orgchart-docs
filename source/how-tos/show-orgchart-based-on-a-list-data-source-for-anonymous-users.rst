Show Org Chart based on a list data source for anonymous users
==============================================================

.. note:: This article is only for `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ for SharePoint 2019 / 2016 / 2013.

In this tip, I will show you how to load Org Chart that based on a list data source for anonymous users on your SharePoint site.

First of all, you need to enable the anonymous access for your web application:

- Open SharePoint Central Administration on your server.
- Under the Application Management section, click the **Manage web applications** link.
- Select one of the available web applications and press the **Authentication providers** button available in the Ribbon. A modal dialog showing the authentication providers available per zone is displayed. In a basic scenario, only the **Default** zone is listed.

.. image:: /../_static/img/how-tos/other-examples/show-orgchart-based-on-a-list-data-source-for-anonymous-users/AuthenticationProviders2.png
    :alt: Authentication Providers

- Click the **Default** link for displaying a modal dialog. Check the **Enable anonymous access** option and press the **Save** button.

.. image:: /../_static/img/how-tos/other-examples/show-orgchart-based-on-a-list-data-source-for-anonymous-users/EnableAnonymousAccessForWebApp2.png
    :alt: Enable Anonymous Access For WebApp


We are done with the first step and now we allowed the anonymous access to our web application.


The next step is granting permissions to anonymous users on the site where our Org Chart based:

- Navigate to the site collections where Org Chart based and go to **Site Settings**. Under the **Users and permissions** section, click the **Site permissions** link.

.. image:: /../_static/img/how-tos/other-examples/show-orgchart-based-on-a-list-data-source-for-anonymous-users/SitePermissionsLocation.png
    :alt: Site Permissions Location

- Press the **Anonymous Access** button in the Ribbon for showing the related configuration modal dialog. In this dialog, you need to choose **Entire Web site** option and uncheck **Require Use Remote Interfaces permission** option. Press the **OK** button.

.. image:: /../_static/img/how-tos/other-examples/show-orgchart-based-on-a-list-data-source-for-anonymous-users/AnonymousAccessRibbonLocation.png
    :alt: Anonymous Access Ribbon Location

.. image:: /../_static/img/how-tos/other-examples/show-orgchart-based-on-a-list-data-source-for-anonymous-users/SetPermsForAnonymousUsersOnSite.png
    :alt: Set Perms For Anonymous Users On Site

After these simple steps, we can see a new group called **Anonymous users** in the list of site permissions. That means anonymous users have access to the site collection.

We need to do just one more thing before the users will see Org Chart in anonymous mode. We need to allow operations for getting items from lists for anonymous users.

For that you need to execute the following PowerShell commands on your SharePoint server:

.. code:: javascript

    $webApplication = Get-SPWebApplication -Identity "<YourWebApplicationAddress:port>"
    $webApplication.ClientCallableSettings.AnonymousRestrictedTypes.Remove( [Microsoft.SharePoint.SPList],"GetItems")
    $webApplication.Update()


That is all! From this moment all users with the anonymous access will see you Org Chart that based on a list data source.


