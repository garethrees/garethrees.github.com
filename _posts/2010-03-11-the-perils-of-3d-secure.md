---
layout: post
title: The Perils of 3D Secure
---

# {{ page.title }}

Some notes and links about implementing 3D Secure.

Not Secure
----------

It has been found that the system is not secure and reported many issues with the authentication process.

Study by Cambridge University:

<http://www.cl.cam.ac.uk/~rja14/Papers/fc10vbvsecurecode.pdf>

> a textbook example of how not to design an authentication protocol. It ignores good design principles and has signiﬁcant vulnerabilities, some of which are already being exploited.

Development Time
----------------

There does not seem to be a suitable solution to the problem. Our current platform has not found a solution and moving platforms could take a couple of weeks - if not more - of our time.

Shopify - lead developers of our online transaction plugin:

<http://support.myshopify.com/discussions/questions/1760-3d-secure>

> It will be ready when it will be ready': this is what I was told a few days ago when I asked the developers

> Developers are very much aware that a deadline is around the corner.

Some forks of the plugin we use appear to have been updated with support for 3D Secure, but none offer documentation or proven success record. Using a different version may also conflict with the existing functions.

Other companies refusing to comply with 3D Secure
-------------------------------------------------

Amazon: No 3D secure

<http://www.amazon.com/gp/help/customer/display.html/ref=hp_lnav_dyn?ie=UTF8&nodeId=518224>

> Amazon.com does not currently support the Verified by Visa program.  You can still use your Visa credit card as payment for an order, but you won't be asked to enter your Verified by Visa password.

Google Checkout: Removal of Maestro payment method

[https://checkout.google.com/support/bin/answer.py?hl=en-uk&answer=105916/](https://checkout.google.com/support/bin/answer.py?hl=en-uk&answer=105916/)

Relatively Low Chargebacks
--------------------------

> We have only had around 7 chargebacks costing £39 each since the apparent move over in November 2009. _- Alex (Finance)_

Loss of Customers
-----------------

Since introducing 3D secure authentication on to their website, different shops have reported a loss of payments due to the 'hassle' that is involved.

<http://econsultancy.com/blog/3887-verified-by-visa-a-conversion-rate-killer>

> After introducing the Verified by Visa scheme to the site, he experienced an immediate 6% drop in conversion rates

One case of 60% losses:

<http://www.northsouthmedia.co.uk/blog/3d-secure-might-bust-your-conversions/>

> It was when the customer was in the payment processing page they the sale.

Banks Moving to Visa
--------------------

RBS

<http://www.rbs.co.uk/personal/current-accounts/g2/debit-cards/your-card.ashx>

> We are replacing our existing Maestro, Solo and Cirrus debit cards with Visa Debit cards

Natwest

<http://www.natwest.com/personal/current-accounts/g4/cards/yourcard.ashx>

> We are replacing our existing Maestro, Solo and Cirrus debit cards with Visa Debit cards

Ulster Bank

<http://www.ulsterbank.com/ni/personal/daily-banking/current-accounts/card/visa-debit.ashx?coid=UB_UK_HPLHS_ni_visadebit>

> Starting in Autumn 2009 and continuing throughout 2010, we are changing all of our Maestro and Solo cards to Visa Debit cards.
