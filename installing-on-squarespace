# How to install Better Brand widget on squarespace
This guide explain how to add the required Better Brand widgets to a squarespace site for running a campaign. The starting point is expected to be that you have entered the editing mode of the squrespace website where you want to add the campaign.

## Step 1: Adding the BB development kit
Navigate to Settings -> Advanced -> Code Injection.

Add the following code to the 'HEADER' section. If there is existing code in the box, add the snippet below existing snippets.
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

Don't forget to press save in the top left corner.

## Step 2: Adding the pop-up on order confimertion page.
> Note: For the pop-up to work you need to have completed step 1.

This is the pop-up that will appear on the order confirmation page after an order is made.

Navigate to Settings -> Advanced -> Code Injection.

Add the following snippet to the "ORDER CONFIRMATION PAGE" section.
```
<!-- Better Brand confirmation start -->
<div 
  class="BB-popup" 
  data-order-subtotal="{orderSubtotal}" 
  data-order-id="{orderId}"
></div>
<!-- Better Brand confirmation end -->
```
> Note: The varaibles `{orderSubtotal}` and `{orderId}` is Squarespace provided varaibles and will be replaced with the right values.

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
