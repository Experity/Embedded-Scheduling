# ClockwiseMD Embedded Scheduling

---

## Setup
Place the script tags in the code snippet below into the `head` section of your
HTML page.

Replace the `<GROUP_ID>` in both places with your group ID.

Replace the `<API_ACCESS_TOKEN>` with your Api Access key.

If you don't know your Api Access key, it can be found by going to the
settings page of any hospital in your group. Once you are at this page, click
on the `Scheduled Care` link and click the `Scheduled Care Off` button. This
will turn the button green and the wording will say `Scheduled Care On` and
there will be a link named `Groups Page`.

Click on the `Groups Page` link. This will take you to a new page. Inspect
this new page to find the code snippet below in the `head` section of the
page. It will include your Api Access key in the `token` field.


---

## Demonstration
[Click here to see the example](https://examples.clockwisemd.com/Embedded-Scheduling/)

---

```html
<!DOCTYPE html>
<html>
  <head>
    <script>
      var _clockwise = {
        host: 'www.clockwisemd.com',
        group_id: <GROUP_ID>,
        token: <API_ACCESS_TOKEN>,
        filters: ["reasons", "location", "physician"],
        showHeader: true
      };
    </script>
    <script src="//www.clockwisemd.com/groups/<GROUP_ID>/schedule.js"></script>
  </head>
  <body></body>
</html>
```
