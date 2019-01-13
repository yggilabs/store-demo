---
layout: content
client_id: '09f822f418c5b2c27fbd'
redirect_uri: https://us-central1-cart-991a0.cloudfunctions.net/api/github/yggilabs/store-demo/authorize
---

<meta name="amp-link-variable-allowed-origin" content="https://us-central1-cart-991a0.cloudfunctions.net">

# store-demo

## Installation
1. Create a fork --- Navigate to the [base project](https://github.com/yggilabs/store-demo). Click the "Fork" button.
2. Enable hosting --- Go to [Settings](../../settings) > GitHub Pages > Source. Change dropdown value to "master branch" and click "save". Installation Done!
3. Change Site Name --- Make this something memorable. Even if you use a custom domain later on. This is the &lt;your-name-here&gt;.github.io

## Basic Configuration

1. Setup Accounts
  If you dont already have these accounts, you may want to set them up now. They will be needed later on.
    1. [GitHub](https://github.com/join)
    2. [Stripe](https://dashboard.stripe.com/register)
2. Authorize accounts
  Give access to the shopping cart app so it can use your accounts
    1. <a href="https://github.com/login/oauth/authorize?client_id={{ page.client_id }}&state=CLIENT_ID(cart)&redirect_uri={{ page.redirect_uri}}" data-amp-replace="CLIENT_ID">GitHub</a>
    2. <a href="https://connect.stripe.com/oauth/authorize?response_type=code&client_id={{ page.client_id }}&state=CLIENT_ID(cart)&scope=read_write" data-amp-replace="CLIENT_ID">Stripe</a>
    
## Adding products

## Advanced coniguration 

## FAQS

### Fixing a mistake

Before we get too far let's ackknowledge something, you will make a few mistakes setting this up. Don't worry! Most CMS can be quite difficult to roll back changes because they are so complicated and rely on hidden information. However, everything here only depends on the files you can see. So, all we need to do is make the files look the same as before and everything is fixed. Luckily, every previous version of your site has been saved. You can go back to any of them at any time.

To revert the most recent change click [here]()

### Edit Config

[here](../../edit/master/_config.yml)

### Create a new product


```markdown
---
label: snake eyes
description: an energy drink
categories:
  beverage
  energy drink
stock:
  quantity: 0
  status: discontinued
  price:
    value: .99
    currency: USD
--- # end product configuration section
```
[here](../../new/master/_products)
