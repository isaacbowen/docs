# Gatekeeper

{% hint style="info" %}
In a lot of ways, this is where Lightward started.

Gatekeeper was a Shopify app -- an early one, created shortly after Shopify opened their app platform.

It's not running anymore; it was replaced by Locksmith. Gatekeeper was created even before Shopify had a customer model, and when the customer model _did_ appear it made more sense to architect something completely new.
{% endhint %}

**Now available:** [**Gatekeeper**](http://gatekeeperapp.com/)**, the content protection tool for** [**Shopify**](http://shopify.com/)**.**

Gatekeeper is built on [CakePHP](http://cakephp.org/), using an extension of Shopify's [official PHP api](http://github.com/Shopify/shopify_php_api) (to be released in the near future as a Cake component - leave a comment if you're anxious).

#### Version 1.0 features:

* Automatic installation on shop templates
* Single-click protection for pages and products
* To preserve settings, locks can be disabled without deleting
* Username/password or username-only users
* Multiple users per lock
* Automated cache renewal to ensure locked content is up to date

#### Planned:

* SSL support
* Storefront authentication without page reloads
* Customize login message per-lock
* Style gallery for Gatekeeper's login forms and messages
* Global enable/disable
* User import/export

#### ––verbose

This project started out as a value-add for a client who maintains a Shopify storefront. They were looking for a way to lock down a single page of their store, such that only users who had a valid username could enter. Shopify does offer password protection, but it's applied globally - the store is either completely locked, or completely open. Thus, Gatekeeper.

Implementation was somewhat less than straightforward. There are no provisions for local scripting in Shopify, and because [Liquid](http://www.liquidmarkup.org/) is sanely designed it does not provide access to arbitrary HTTP query data (so no POST/GET vars, let alone any session identifiers). This meant that the role that the Shopify storefront could play was limited at best. The solution I arrived at, and what is in production now, involves [metafields](http://api.shopify.com/metafield.html) set on the requested resource (currently implemented for pages/products) and on the shop itself to control whether or not the resource should be delivered from Shopify, or retrieved from Gatekeeper. If the resource is locked, Javascript is used to pull the requested data from Gatekeeper's domain (necessitating JSONP). This data is only delivered if an authenticated user session is active - if not, a login form is returned, which points back to Gatekeeper.

This obviously means that Gatekeeper must actively maintain a cache of resource data, which it does. This same cache powers the lists of resources (again, just pages and products for now) that are offered to the user from the Gatekeeper dashboard, and is regularly validated and renewed. This allows Gatekeeper to capably handle thousands of resources per shop while keeping the user experience responsive, and keeping api calls to a minimum.

Gatekeeper spent exactly three weeks in the approval process. Dennis Theisen handled its review, and provided surprisingly practical and insightful feedback throughout. I'm thoroughly impressed with the level of care that Shopify gives to the user experience, even as it extends beyond Shopify to third-party applications. The [App Store](http://apps.shopify.com/) is a walled garden, yes, but close communication throughout makes this a benefit, not a hindrance.

Gatekeeper is being released today into the wild, with a free one-lock-one-user trial and an unlimited-use subscription for USD$20 per month.
