How Org Chart pulls data from AD On-Premises
============================================


In this article is described how `Plumsail Org Chart <https://plumsail.com/privacy-policy/>`_ communicates with SharePoint User Profile Service and Active Directory and what are prerequisites for Org Chart correct work.


Org Chart displays data directly from User Profile service, but if there are no user profiles, 
Org Chart will simply empty. You can always create user profiles manually, 
but importing them from Active Directory is a much more efficient way. 
Look at the picture for better understanding of this article.

.. image:: /../_static/img/how-tos/additional-resources/how-orgchart-pulls-data-from-ad-on-premises/DataExchange.png
    :alt: Data exchange



Active Directory accounts import is a standard feature of SharePoint User Profile service. 
There are a lot of guides describing in detail how to configure import. 
I would recommend `this one <http://blog.sharedove.com/adisjugo/index.php/2012/07/23/setting-user-profile-synchronization-service-in-sharepoint-2013/>`_ written by Adis Jugo, 
you can also use `guide from Microsoft <http://technet.microsoft.com/en-us/library/ee721049.aspx>`_ .


Once you have configured import, it is enough to get started with Plumsail Org Chart. 
You can `add web part <../installation/office365.html>`_ to a page and choose User Profiles as a data source, your org structure can look like this:


.. image:: /../_static/img/how-tos/additional-resources/how-orgchart-pulls-data-from-ad-on-premises/main.png
    :alt: Main

