# Tags and Variables

If you need to send data from your site to an api via an api call, you can send it to Google Tag Manager via the Data Layer and let it handle the rest. Assuming you've enabled GTM on your site:

## 1. Add GTM variables

Go to the variables tag, add a Data Layer variable

## 2. Add a custom html tag

Go to the tags tab, click new, type: Custom HTML, something like this:

```html
<script>
coolApi.send({
  "thing1": "{{myvar1}}}",
  "thing2": "{{myvar2}}"
});
</script>
```

The vars will be replaced by those sent to the Data Layer. Ensure the tag displays on the page you need, e.g. the checkout success page. Save and publish the version.

## 3. Send data to the dataLayer

```html
<script>
var dataLayer = [];
dataLayer.push({"myvar1": "myvalue1"});
</script>
// ... then GTM script tag further down
```
