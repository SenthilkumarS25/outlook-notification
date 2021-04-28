# Outlook Notification Sample
This sample is based on [this](https://github.com/microsoftgraph/nodejs-webhooks-rest-sample) Microsoft's sample.

This NodeJS web application shows how to subscribe for change notifications as well as how to validate and decrypt change notifications with resource data (preview) when supported by the resource.

[User-delegated authentication](https://docs.microsoft.com/graph/auth-v2-user) represents a user and the application being used when calling the Microsoft Graph. This type of authentication is best suited for scenarios when the user interacts with the application.

The following are common tasks that an application performs with webhooks subscriptions:

- Get consent to subscribe to resources and then get an access token.
- Use the access token to [create a subscription](https://docs.microsoft.com/graph/api/subscription-post-subscriptions) to a resource.
- Send back a validation token to confirm the notification URL.
- Listen for notifications from Microsoft Graph and respond with a 202 status code.
- Request more information about changed resources using data in the notification if no data is provided with the notification.
- Decrypts the resource data provided with the notification if any has been provided with the notification.

## Prepare Development Environment

### Prerequisites

- [Node.js](https://nodejs.org/) version 12 or 14.
- The application ID and key from the application that you [register on the Azure Portal](#register-the-app).
- A public HTTPS endpoint to receive and send HTTP requests. You can host this on Microsoft Azure or another service, or you can [use ngrok](#ngrok) or a similar tool while testing.

### Clone the repository
Open Terminal to clone the repository
```Shell
$ git clone https://github.com/SenthilkumarS25/outlook-notification.git

$ cd outlook-notification
```
### Configure
- Open constants.js.

- Replace `ENTER_YOUR_CLIENT_ID` with the client ID of your registered Azure application.

- Replace `ENTER_YOUR_TENANT_ID` with the ID of your organization. This information can be found next to the client ID on the application management page.

- Replace `ENTER_YOUR_SECRET` with the client secret of your registered Azure application.

- Replace `NGROK_ID` with the value in https public URL from the previous section.

### Install packages
```Shell
$ npm install
```

### Build
```Shell
$ npm run build
```

### Run/Debug
```Shell
$ npm start
```
> **Note:** You can also make the application wait for a debugger. To wait for a debugger, use the following command instead:
>
> ```Shell
> $ npm run debug
> ```
> You can also attach the debugger included in Microsoft Visual Studio Code. For more information, see [Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging).

Open a browser and go to [http://localhost:3000](http://localhost:3000).

## Additional resources

- [Microsoft Graph Webhooks sample for ASP.NET core](https://github.com/microsoftgraph/aspnetcore-webhooks-sample)
- [Microsoft Graph Webhooks sample for Java Spring](https://github.com/microsoftgraph/java-spring-webhooks-sample)
- [Working with Webhooks in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/webhooks)
- [Subscription resource](https://docs.microsoft.com/graph/api/resources/subscription)
- [Microsoft Graph documentation](https://docs.microsoft.com/graph)
