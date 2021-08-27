===============================================
eBay Marketplace account deletion notifications
===============================================

Process overview
================

Since September 2021, **eBay requires supporting customer account deletion/closure notifications**.
As such, when eBay receives an account request for deletion, all eBay partners must confirm the
reception of the request and take further action.

Odoo has a notification endpoint to receive those notifications and handle the first set of actions
to anonymize the account details in Contact and remove the customer's access to the portal.

**However** you need to tell eBay how to contact this endpoint, but don't worry, it's very easy !

.. warning::
   Make sure to correctly set up your subscription to the **marketplace account deletion
   notifications**, as eBay may temporarily disable the related eBay account until the subscription
   is completed.

Configuration
=============

Verify your installation of Odoo is up to date
----------------------------------------------

   - If you are running on premise, you might need to **update your code**.
   - If you are running on SaaS, this solution is **already available**.

Retrieve endpoint details from Odoo
-----------------------------------

The endpoint details can be found in :menuselection:`Sales --> Configuration --> Settings --> eBay`.
Click on *Generate Token* to retrieve your **Verification Token**.

.. image:: deletion_notifications/verification-token.png
   :align: center
   :alt: Button to generate an eBay verification token in Odoo

Log in to your developer eBay account
-------------------------------------

Log in on the `developer portal of eBay <https://go.developer.ebay.com/>`_ and go to **Alerts & Notifications**.

.. image:: ./media/subscribe01.png
   :align: center

To subscribe to deletion/closure notifications, eBay needs a few details:

- An **email address** to send notifications to if the endpoint is unreachable.
- The **endpoint details**:
  - The path to Odoo's account deletion notification endpoint
  - A verification token

.. image:: ./media/subscribe02.png
   :align: center

.. note::
   You can edit the last two fields once the email address field is filled out.

Verify the connectivity with the endpoint
-----------------------------------------

After setting the retrieved endpoint details in eBay's dashboard, consider testing the connectivity
with the **Send Test Notification** button.

You should get the following confirmation message: "A test notification was sent successfully!"

.. image:: ./media/subscribe04.png
   :align: center

