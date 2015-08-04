---
layout: post
title: "Implementing “Sales Products and Manufactured Products” Concept with SAP Banking"
date: 2015-07-18
author: sajeev_khan
tags : 
- SAP
- sap
---

We are living in an era where there is fierce competition between banks. There is a continuous price war for banking products and services between the various players and it is catching up with the pricing war in the retail industry. While this has an impact on the profit margins of banks and financial Services companies, it is also a great opportunity to attract new and retain existing customers by offering flexible pricing models that are tailored for individuals or customer groups.

Ok. Now what does it take to be leaders in this game. You have to have agile IT systems based on which you can launch these pricing models to the market much faster than your competition. The pricing engine in SAP Banking Services is a classic example of a robust pricing engine which caters to your ever increasing demand for flexible pricing models which will differentiates you from other players.

There are three components in your IT landscape which are critical to meet the above demands:

	1. An agile Sales System (Account Origination) which is able to push new pricing models to the market.
	2. A core banking system which can support the concept of Sales Products and Manufactured Products.
	3. A state of the art Pricing Engine alongside or within your core banking system.


Last year, I was asked to put together a proposal for implementing a pricing solution based on the concept of Sales Products and Manufactured Products, around the Pricing Engine in SAP Banking Services Solution. This prompted me to write about this topic.

In this article, I would like to touch upon the concept of Sales Products and Manufactured Products in Banking and the overall architecture of how this can be realized in a Banking IT Landscape. As always, I will give you an overview of how this is realized in the SAP Banking world.

Now, what’s a Sales Product in Banking? Well, you already know it. Sales Products are products which are on the current sales catalogue of a bank. These are products which exist in account origination systems and the characteristics of these products are defined from a sales perspective.

So, what’s a manufactured product? Manufactured Products are products with distinct characteristics in the core banking system which are capable of operating as a generic product in a family of products and can accommodate all or most variations of characteristic of the sales product within that family of products. Examples of Manufactured Products are Current Accounts, Term Deposits, and Loans etc. Manufactured Products are also referred to as Operational Products.

The graphic below depicts the business architecture of how this concept is realized in a banking IT system landscape.


![Pricing Engine]({{site.url}}{{site.baseurl}}/assets/posts/pricing_engine.jpg)

As per the diagram above, sales products exists in your sales product catalogue and it refers the price list in the central pricing engine. When the sales process is completed and the application is converted to a contract, the account is created in the core banking system. The sales product is mapped to the manufactured product and the account is created based on the manufactured product but it’s linked to price list which was used in the sales process.


Following are some of the key characteristics of a sales product:


	* Sales Products have shorter lifecycle; Lifecycle of the product version ends as soon as the product is off the sales catalogue.
	* Products are bundled according to current sale trends.
	* Products Classified according to various criteria including Sales Channel, Sales Organization, Customer Groups/Eligibility.
	* Pricing of Products are based Up to Date Sale Prices, Discounts based on Promotions, Listed Prices, Negotiated Prices etc.
	
	
Following are some of the key characteristic of a manufactured product

	+ They are products which were already sold and for which accounts still continue to operate.
	+ Manufactured products typically have a Longer Lifecycle; Product is active as long as an account based on the product is active.
	+ Product definition covers all features and conditions to cover the entire life cycle of the product
	+ Pricing: Broad price ranges to accommodate product origination from various sources
	+ Multiple sales products can be mapped to a manufactured product.
	

Now, let’s look briefly at how this works in the SAP world.

![SAP CRM]({{ site.url}}{{ site.baseurl }}/assets/posts/sapcrm.jpg)


As per the concept of sales products and manufactured products, the cardinality between the two is N: 1. This means that when an Account Contract is created in SAP Banking Services it needs to be mapped to the appropriate Sales Product and the Account Contract in SAP Banking Services will need to hold the identifier of the Sales Product to which it belongs to. During the operational processes in SAP Banking Services for account contracts, the Financial Conditions maintained in the Product Pricing List will be fetched for the sales product will be picked up for execution of the operational process.


Following are process steps for the determination of sales product based pricing for operational processes in SAP Banking Services:


	1. On conclusion of the account origination Process where the contract is finalised, an account contract is created in SAP Banking Services based on the Manufactured Product.
	2. The sales product identifier is persisted on the account contract in SAP Banking Services
	3. Whenever the Pricing information is required for any operation processes in SAP Banking Services for the account contract, the sales product identifier will be passed to the price determination module in SAP Banking Services so that the appropriate Sales Product based Pricing List is fetched.
	4. The pricing engine and product configurator in SAP Banking Services makes all this possible in a seamless manner. So, go ahead and explore it further to discover how you can leverage this concept to rapidly launch new pricing models to the market.


---

*All content provided on this blog is for informational purposes only. The owner of this blog makes no representations as to the accuracy or completeness of any information on this site or found by following any link on this site. The owner of this blog will not be liable for any errors or omissions in this information nor for the availability of this information. The owner will not be liable for any losses, injuries, or damages from the display or use of this information*

