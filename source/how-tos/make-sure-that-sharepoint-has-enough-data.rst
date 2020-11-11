How to make sure that User Profile Service has enough data
==========================================================

Firstly, verify User Profile Service for the current SharePoint Farm. Open SharePoint Central Administration:

.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/CentralAdministrationLink.png
    :alt: Central Administration Link



.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/CentralAdministrationRunAs.png
    :alt: Central Administration


Navigate to ‘Manage service applications’:


.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/ManageServiceApplications.png
    :alt: Manage Service Applications


Open User Profile Service Application:


.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/UserProfileServiceLink.png
    :alt: User Profile Service Link


.. note:: The name of the User Profile Service can be different, look at the type to be sure.


Check number of user profiles in the top right corner of the page:


.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/NumberOfProfiles.png
    :alt: Number Of Profiles


If number of profiles is relatively small, check synchronization with Active Directory.

If you have specific person, which will be the root of the hierarchy, navigate to ‘Manage User Profiles’:


.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/ManageUserProfiles.png
    :alt: Manage User Profiles


Then find the profile for the root person:

.. image:: /../_static/img/how-tos/additional-resources/make-sure-that-sharepoint-has-enough-data/FindSpecificProfile.png
    :alt: Find Specific Profile


If the profile of the root person found you can use information about this person `for filtration in the configuration wizard <../configuration-wizard/filtration.html>`_ . 
If the profile not found, please choose another user profile as root or check synchronization with Active Directory.


In the configuration wizard make sure that filtration rule does not exclude the root person from the hierarchy. Please read description of filtration syntax for your data source:

- Filtration rules syntax for User Profiles (link)
- Filtration rules syntax for SharePoint list (link)