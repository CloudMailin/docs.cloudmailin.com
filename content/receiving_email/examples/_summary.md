### Summary

That's the code complete. All we now have to do is log into [CloudMailin] and make sure we
set your address to deliver to `http://example.com/incoming_mail` (replace example.com with your App URL) and send our first message.

![Inbound Dashboard](/assets/images/inbound_summary.png)

All of the details are listed in the dashboard.
Here we can dig in and see the details.
If the HTTP response of your server does not return a 2xx status code then the response
will be recorded (see [Status Codes]):

![Inbound Error Example](/assets/images/inbound_error_details.png)
