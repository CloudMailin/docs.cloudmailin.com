---
title: Receiving Your Email as an HTTP POST - Formats
---

# Receiving Your Email as an HTTP POST

CloudMailin sends your email as an HTTP POST to the URL that you specify. There are several formats to choose from:

| Format                 | Details                                             | Description                                                                                      |
|------------------------|-----------------------------------------------------|--------------------------------------------------------------------------------------------------|
| `Multipart Normalized` | [details](/http_post_formats/multipart_normalized/) | A new `multipart/form-data` based format consisting of four main parts `envelope`, `headers`, `body`, `attachments`. this normalizes headers and arrays to make things more consistent. We recommend using this as the default for new projects. |
| `JSON Normalized`      | [details](/http_post_formats/json_normalized/)      | Exactly the same as the `multipart` format but this uses `JSON` to encode the details it normalizes headers and arrays to make things more consistent. We recommend using this as the default for new projects. |                                                                                        |
| `Raw Message`          | [details](/http_post_formats/raw/)                  | This sends just original Raw message as a single `multipart/form-data` request parameter.        |
| `Multipart`            | [details](/http_post_formats/multipart/)            | An older `multipart/form-data` based format consisting of four main parts `envelope`, `headers`, `body`, `attachments`. |
| `JSON`                 | [details](/http_post_formats/json/)                 | An older `JSON` format, the same as the `multipart` format but this uses `JSON` to encode the details.           |
| `Original`             | [details](/http_post_formats/original/)             | The original CloudMailin message format (only recommended for legacy projects).                  |

If you have an existing app using CloudMailin then continuing to make use of the [Original Format](/http_post_formats/original/) makes sense. If you're starting a fresh app then their the [Multipart](/http_post_formats/multipart/) or [JSON](/http_post_formats/json/) formats will be useful depending on whether you prefer to work with JSON or not. We recommend using the multipart format though as it's generally the easiest to work with in modern web frameworks.

If you just want to use CloudMailin to forward the entire email to your website over http without parsing or processing it at all then the [Raw format](/http_post_formats/raw/) does exactly that.

## Testing a Format

If you want to see how a format will look with your own content we recommend using the [WebhookApp](http://webhookapp.com). Simply set the [WebhookApp](http://webhookapp.com) as your message url target and then send an email. The message content will then be sent over HTTP to the app using WebSockets so you can view this content and try out the format.
