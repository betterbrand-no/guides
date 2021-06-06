# How to install Better Brand widget on a website
This guide explain how to add the required Better Brand widgets to a website for running a campaign. The widget requires you to be able to add a snippet to the `head` and `body` of the document.

## Step 1: Adding the BB development kit
Right before the `</head>` in the document add the following snippet:
```
<!-- Better Brand SDK start -->
<script>
  window.BB = window.BB || {
    cmpId: 'YOUR_CAMPAIGN_ID'
  };
</script>
<script async defer src="https://sdk.betterbrand.no/bb.js"></script>
<!-- Better Brand SDK end -->
```
Replace YOUR_CAMPAIGN_ID with the campaign id provided by Better Brand. Note: The campaign id should be in quatation marks as showed above.
This will make sure to load the Better Brand SDK to the page.

## Step 2: Adding the Better Brand Pop-up to the order confirmation page.
> Note: For the pop-up to work you need to have completed step 1.

This is the pop-up that will appear on the order confirmation page after a pruchase have been successfully made.

Add the following snippet right after `<body>` or right before `</body>` in the document for your order confirmation page.

```
<!-- Better Brand confirmation start -->
<div 
  class="BB-popup" 
  data-order-subtotal="{orderSubtotal}" 
  data-order-id="{orderId}"
></div>
<!-- Better Brand confirmation end -->
```
**IMPORTANT:** You need to provide the `{orderSubtotal}` and `{orderId}` varaibles. `orderId` should be the final order id and unique for the purchase made. This is used for making sure an valid order is made. `orderSubtotal` should be the sub total value of the purchase made.

### Optional: Update default texts in popup
By default Better Brand provide texts for the different sections on the pop-up. You can overwrite these with an extra set of data attributes if wanted.

#### Pop-up headline text
**Default**: Vi støtter ditt formål.

Add a `data-headline-text` attribute to the pop-up with the text of your choise if you want to change this. E.g.:
```
<!-- Better Brand confirmation start -->
<div 
  class="BB-popup" 
  data-order-subtotal="{orderSubtotal}" 
  data-order-id="{orderId}"
  data-headline-text="Your custom text goes here!"
></div>
<!-- Better Brand confirmation end -->
```
#### Cause selector description text
**Default**: Når du handler hos oss, bidrar vi til formålet du velger.

Add a `data-description-text` attribute to the pop-up with the text of your choise if you want to change this. E.g.:
```
<!-- Better Brand confirmation start -->
<div 
  class="BB-popup" 
  data-order-subtotal="{orderSubtotal}" 
  data-order-id="{orderId}"
  data-description-text="Når du handler hos oss går 5% av prisen til å støtte formålet du velger."
></div>
<!-- Better Brand confirmation end -->
```
#### Donation confirmation text
**Default**: Vi har gitt ${donation} ${currency} til ditt formål! På vegne av ${cause}, så takker vi deg for ditt bidrag.

- `${cause}` is automatically replaced with the organization name, e.g. Rødekors.
- `${donation}` is automatically replaced with the amount donated based on the purchase, e.g. 10 if the donation percentage is 10% and the user purchased for 100.
- `${currency}` is automatically replaced with by the ISO 4217 currency code for the selected currecny on the campaign, e.g. NOK if Norwegian Kroner is selected.

Add a `data-confirmation-text` attribute to the pop-up with the text of your choise if you want to change this. E.g.:
```
<!-- Better Brand confirmation start -->
<div 
  class="BB-popup" 
  data-order-subtotal="{orderSubtotal}" 
  data-order-id="{orderId}"
  data-confirmation-text="Vi har donert ${donation} kr til ${cause}! Takk for ditt bidrag"
></div>
<!-- Better Brand confirmation end -->
```
Note how you can use the `${donation}`, `${cause}`, and `${currency}` variables.

Don't forget to press save in the top left corner when you have made changes.

# General technical specifications
## How the SDK is loaded
The Better Brand JavaScript SDK is loaded asynchronously and is deferred meaning it will have minimal influence on load and execution performance. The SDK is tested on and supports the latest two versions of the most popular browsers: Chrome, Firefox, Edge, Safari (including iOS), and Internet Explorer (version 11 only). The assets and images are delivered on a global content delivery network with more than 200 edge locations, so it will load quickly whereever the user is on the globe. 

## Styling
The Better Brand SDK is not injecting any iframes as we want the webshops to have more control over the look and feel of the widgets. The Pop-ups can be fully customized using css.

## Cookies and personal information
Better Brand is not using any cookies, and no personal data from the consumer is sent to our servers. We are only requiring the OrderID to be sent with the confirmation as we use this to make sure a order was made.
