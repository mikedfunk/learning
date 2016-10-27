# Tags and Variables

If you need to send data from your site to an api via an api call, you can send it to Google Tag Manager via the Data Layer and let it handle the rest. Assuming you've enabled GTM on your site:

## 1. Install GTM

Go to [tag manager](tagmanager.google.com), click the GTM-XXXXXX link at the top right next to publish. It will give you a script tag to paste into your site template.

## 2. Add GTM variables

Go to the variables tag, add a Data Layer variable

## 3. Add a custom html tag

Go to the tags tab, click new, type: Custom HTML, something like this:

```html
<script>
coolApi.send({
  "thing1": "{{myvar1}}",
  "thing2": "{{myvar2}}"
});
</script>
```

The vars will be replaced by those sent to the Data Layer. Ensure the tag displays on the page you need, e.g. the checkout success page. Save and publish the version.

## 4. Send variable data to the dataLayer

```html
<script>
var dataLayer = [];
dataLayer.push({"myvar1": "myvalue1"});
</script>
// ... then GTM script tag further down
```
