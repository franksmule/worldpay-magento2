Worldpay Online Payments Magento 2
==================

Worldpay Online Payments Magento Module - Version 2.0.16

Tested versions..

Magento 2.0.0 - 2.0.4

### Installation 

composer require worldpay/magento2-module-payments 

Creates database and clears cache 

php bin/magento setup:upgrade  
php bin/magento cache:clean


How To use
================
Login to your Magento Admin Panel.
Go to Stores -> Configuration.
On the left menu select the sales section, and click Payment Methods, then scroll down in the list and find Worldpay Payments.

Add your keys, which you can find in your Worldpay dashboard (Settings -> API keys). Change Enabled to Yes, set your title and payment descriptions to what you would like the user to see.

In your Worldpay dashboard, (Settings -> Webhooks) add a webhook to your Magento URL.
For example;
http://www.mywebsite.com/index.php/worldpay/notification/

Changing www.mywebsite.com to your website URL. Visiting this URL should show OK is similar. Your URL most be externally accessible.

If you change your API keys in future, you may need to clear the Magento cache for it to take affect immediately.

Configuration options
================

Enabled
=====
Enable / Disable the module

Settlement Currency
=====
Choose the settlement currency that you have setup in the Worldpay online dashboard.

Use 3D Secure
=====
Process 3D secure payments for front end card orders

Payment Action
=====
Setting to Authorize only; will require you to enable authorisations in your Worldpay online dashboard.
You will then be able to capture the payment when you create an invoice in Magento.
You can only capture once, of any amount up to the total of the order.

Setting to Authorize and Capture; will capture the order immediately.

Enable Debug
=====
This should be set to 'no' in normal circumstances. If you need support we may ask you to enable this.

Store customers card on file
=====
A reusable token will be generated for the customer which will then be stored. This will allow the customer to reuse cards they've used in the past. They simply need to re-enter their CVC to verify. They can view their stored cards in My Account.

New order status
=====
Your Magento order status when payment has been successfully taken

Title
=====
The title of the module, as appears in the payment methods list to your customer. You can set this to blank to show no title.

Payment Description
=====
Payment description to send to Worldpay.

Environment Mode 
=====
Test Mode / Live Mode - 
Which set of service and client keys to use on the site

Test, Live - Service & Client keys
=====
Your keys, which can be found in your Worldpay dashboard.

Troubleshooting
=================
I cannot find 'Worldpay Payments' in the configuration page.  
--- Make sure you have uploaded the module into the root directory  
--- Clear Magento cache  
--- Resave your user  
--- Logout and log back in  

When I click 'Worldpay Payments' it responds with a 404 error.  
--- Clear Magento cache  
--- Resave your user  
--- Logout and log back in  

How to resave user  
System -> Permissions -> Users -> Click your user -> Click save user  

How to clear Magento cache  
System -> Cache Management -> Click Flush Cache Storage  


Changelog
================

##### 2.0.16
APM notification fix

##### 2.0.15
New APMs

##### 2.0.1
Use composer version of Worldpay PHP Lib

##### 2.0.0
Initial Release