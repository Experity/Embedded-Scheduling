# ClockwiseMD Embedded Scheduling

---

## Setup
Place the script tags in the code snippet below into the `head` section of your
HTML page.

Replace the `<GROUP_ID>` in both places with your group ID.

Replace the `<API_ACCESS_TOKEN>` with your Api Access key.

Replace the `<CONTAINER_ID>` with the `id` of the html div in which you would like
to render the widget. _* Remove all styling to this div for best results._

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
        showHeader: false,
        showFooter: false,
        containerId: <CONTAINER_ID>
      };
    </script>
    <script src="//www.clockwisemd.com/groups/<GROUP_ID>/schedule.js"></script>
  </head>
  <body></body>
</html>
```

## Advanced Options
You can add the following options to your `_clockwise` config object for more
fine-grained control.

```
'appointmentQueueId (default none)'     // Restricts scheduled care to one queue
'includeClockwiseStyles (default true)' // Set to `false` if you'd like to
style the HTML yourself.
'showProviderInfo (default true)'       // When set to `false`, provider image,
bio, and profile link, will not be rendered.
'numVisibleDays (default 7)'            // Number of days in the schedule to show
at a time. Note: This value is dynamically changed on smaller screens (iPad,
iPhone, etc).

Ex.

var _clockwise = {
  ... same as above ...
  appointmentQueueId: <APPOINTMENT_QUEUE_ID>,
  includeClockwiseStyles: false,
  showProviderInfo: false,
  numVisibleDays: 3
}
```

---

## Basic CSS
Here are some basic styles to get you started if choose not to include clockwise
styles.

```css
<style>
.provider-time {
  border: 1px solid #5395c3;
  color: #5395c3;
  padding: 5px;
  margin: 5px;
  display: block;
  text-decoration: none;
}
.provider-schedule {
  display: inline-block;
  background: #f9f9f9;
  border-radius: 4px;
  border: 1px solid #b0b0b0;
  position: relative;
  width: 100%;
  text-align: center;
}
.provider-day-schedule {
  display: inline-block;
  padding: 10px;
  text-align: center;
  min-width: 116px;
}
.scrollable-times {
  height: 230px;
  overflow-y: auto;
  padding: 0 5px;
}
.day-change-btn {
  padding: 6px 10px 8px 10px;
  margin: 5px;
  border-radius: 4px;
  background: rgba(211, 211, 211, 0.49);
  border: 1px solid #b0b0b0;
  font-size: 15px;
  color: grey;
}

.day-change-btn.active:hover {
  cursor: pointer;
  background: lightgrey;
}

.day-change-btn.inactive {
  opacity: 0.3;
}
</style>
```
