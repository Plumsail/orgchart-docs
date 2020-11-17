How to display Skype for Business (Lync) presence for Org Chart in SharePoint and Microsoft Teams
=================================================================================================

.. note:: thas currently the Skype for Business (Lync) status can be displayed on Classic pages only.
The code below will not work for Modern UI pages.

Here’s a snippet for tooltip template which allows to display presence inside tooltip:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-skype-for-business-lync-presence/LyncPresence.png
    :alt: Lync Presence

You can customize HTML templates for boxes, tooltips and search results. 
See the documentation (link) for more information.

You can use this code snippet even in box template. The article below describes how it works but you can use it as is without modificaitons, just copy paste to your HTML template.

.. code-block:: html

  <div class="pl-item-photo">
   {{#if PictureURL}}
    {{#if PersonalURL}}
     <a href="{{PersonalURL}}" target="_blank">{{safeImage PictureURL}}</a>
    {{else}}
     {{safeImage PictureURL}}
    {{/if}}
   {{/if}}
  </div>
  <div class="pl-item-fields">
   <div class="field-container header-field">
   {{#if SPS-SipAddress}}
    <span class="ms-imnSpan">
     <a href="#" class="ms-imnlink ms-spimn-presenceLink">
      <span class="ms-spimn-presenceWrapper ms-imnImg ms-spimn-imgSize-10x10">
       <img name="imnmark" onload="IMNRC('{{SPS-SipAddress}}')" title="" showofflinepawn="1" class="ms-spimn-img ms-spimn-presence-disconnected-10x10x32" src="/_layouts/15/images/spimn.png" alt="Offline" sip="{{SPS-SipAddress}}" id="imn_{{UserProfile_GUID}},type=sip">
      </span>
     </a>
    </span>
    <span class="ms-noWrap ms-imnSpan">
     <a href="#" class="ms-imnlink" tabindex="-1">
      <img name="imnmark" title="" onload="IMNRC('{{SPS-SipAddress}}')" showofflinepawn="1" class="ms-hide" src="/_layouts/15/images/spimn.png" alt="No presence information" sip="{{SPS-SipAddress}}" id="imn_{{UserProfile_GUID}}_2,type=sip">
     </a>
    <a target="_blank" class="ms-subtleLink" href="{{PersonalURL}}">
     {{PreferredName}}
    </a>
   </span>
   {{else}}
    <a target="_blank" href="{{PersonalURL}}">{{PreferredName}}</a>
   {{/if}}
   </div>
   <div class="field-container ">
    {{Title}}
   </div>
   <div class="field-container ">
    {{Department}}
   </div>
   <div class="field-container ">
    <a href="mailto:{{WorkEmail}}">{{WorkEmail}}</a>
   </div>
   <div class="field-container ">
    {{WorkPhone}}
   </div>
   <div class="field-container ">
    {{Office}}
   </div>
   {{#if PersonalURL}}
    <div class="personal-page-link">
     <a href="{{PersonalURL}}" title="Navigate to personal page" target="_blank">View profile</a>
    </div>
   {{/if}}
  </div>


You can find the snippet which I provided earlier inside this template. This snippet renders presence indicator and name of employee with link to user profile.

You may also need to add this code to **Custom CSS** step of the configuration wizard:

.. code-block:: css

  .ms-hide{
    display: none!important;
  }