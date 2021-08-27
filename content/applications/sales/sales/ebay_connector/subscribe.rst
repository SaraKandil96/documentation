=============================================================================
How to subscribe to eBay marketplace account deletion/closure notifications ?
=============================================================================

Process overview
================

Since Septembre 2021, eBay requires supporting customer account deletion/closure notifications. As such, when eBay receives an account request for deletion, it requests all eBay partners to confirm reception of the request and take further actions.

Odoo has developed an endpoint to receive those notifications and handle a first set of actions to anonymise the account details in Contact and remove his access to the portal.

**However** you need to tell eBay how to contact this endpoint, but don't worry, it's very easy !

.. important::
   If eBay doesn't have details to sent account deletion/closure notifications to, the related eBay account can be temporarily disabled by eBay until subscription completes.

Subscribe to eBay marketplace account deletion/closure notifications
====================================================================

Make sure you are up-to-date
----------------------------

   - If you are running on premise, you might need to **update your code**.
   - If you are running on SaaS, this solution is **already available**.

Retrieve endpoint details from Odoo
-----------------------------------

The endpoint details can be found in :menuselection:`Sales --> Configuration --> Settings --> eBay`.
Note you will need to use the "Generate Token" button to get your Verification Token.

.. image:: ./media/subscribe03.png
   :align: center

Log in to your developer eBay account
-------------------------------------

Log in on the `developer portal of eBay <https://go.developer.ebay.com/>`_ and go to **Alerts & Notifications**.

.. image:: ./media/subscribe01.png
   :align: center

In order to subscribe to deletion/closure notifications eBay needs a few details:

   - An **email address** to sent notification to (only in case of the endpoint is unreachable)
   - And most importantly, the **endpoint details**:
      - The path to Odoo's account deletion notification endpoint
      - A verification token

.. image:: ./media/subscribe02.png
   :align: center

.. important::
   The two last fields won't be editable until you provide an email address (first field).

Verify the connectivity with the endpoint
-----------------------------------------

After setting the retrieved endpoint details in eBay's dashboard, consider testing the connectivity by using the **Send Test Notification** button.

Doing so, it should display the following confirmation message.

.. image:: ./media/subscribe04.png
   :align: center

