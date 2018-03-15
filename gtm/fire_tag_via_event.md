# Fire a tag via an event

If you need to send data from your site to an api via an api call, you can send it to Google Tag Manager via the Data Layer and let it handle the rest. Assuming you've enabled GTM on your site:

## 1. Install GTM

Go to [tag manager](tagmanager.google.com), click the *GTM-XXXXXX* link at the top right next to publish. It will give you a script tag to paste into your site template.

## 2. Add GTM variables

Go to the variables tag, add data Layer variables e.g. `myvar1` and `myvar2`. You'll also need to add a variable for the event name e.g. `myevent1`.

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

The vars will be replaced by those sent with the event when it is fired. 

## 4. Create a trigger

In the *Triggering* area, select *Custom Event* and create a new event. Give the trigger an event name like `My Event 1`. In the *This trigger fires on* area, select *event equals {my_event_var_name}* with the select form elements, where `{my_event_var_name}` is the variable you set up for the event earlier (in this case `myevent1`).

## 5. Send variable data to the dataLayer

```html
<script>
window.dataLayer.push({"event": "myevent1", "myvar1": "myvalue1", "myvar2": "myvalue2"});
</script>
```

This should fire the trigger, passing data. The trigger is listening for this specific event variable name, so it will only trigger when this event is passed to the data layer. The tag is only fired on that trigger and will have accesss to all variables in the data layer including any of these new ones like `myvar1`. Try a console.log if you need to test.
