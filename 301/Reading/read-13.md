# Read: 13 - Update/Delete
#### 6/16/20

- [Sending Form Data](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)
- [Forms in HTML5](https://htmlreference.io/forms/)
- [Styling HTML Forms](https://www.youtube.com/playlist?list=PL4cUxeGkcC9g5_p_BVUGWykHfqx6bb7qK)

## Client/server architecture
- An HTML form on a page is a convenient user-friendly way to configure an HTTP request to send data to a server.

## On the client side:
- a `<form>` element defines how the data will be sent.
### Action
- the acton attributes defines where the data gets sent.
    - If this attribute isn't provided, the data will be sent to the URL of the page containing th form.
### Method
- Defines how the data is sent.
    - GET
    - POST
### HTTP requests
- HTTP requests are never displayed to the user. 
    1. Open the developer tools.
    1. Select "Network"
    1. Select "All"
    1. Select "foo.com" in the "Name" tab
    1. Select "Headers"
## Sending Files via HTTP is a special case
- To send a file there are 3 extra steps
    1. Set the method to POST - file cant be in the URL parameters
    1. Set the value of enctype to multipart/form-data
    1. Include 1 or more `<input type="file">` controls to allow your users to select teh files that will be uploaded. 
## Security
- Be Paranoid: Never trust your users
    - Escape potentially dangerous characters
    - Limit the incoming amount of dat to allow only what's necessary
    - Sandbox uploaded files.