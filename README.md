# Sam.js - Seriously Awesome Modules

### installation
```sh
yarn add samjs-components
```

## Cookie Toaster - Makes tasty cookies for React.

### use
In your root component:
```js
import { CookieToaster } from 'samjs-components'
...
<CookieToaster />
...
```

To modify the css you can use the following structure:
```scss
.cookie-toaster { // or cookie-toaster-modal, cookie-toaster-top
   // topmost div
  .cookie-container {
    // inner content

    h1{
      // title css
    }

    p{
      // text css
    }

    a{
      // link css
    }

    button {
      // button css
    }
  }
}
```

### components
- CookieToaster
- CookieToasterTop
- CookieToasterModal

### props
- title: String, title (duh)
- text: String, content
- btnAcceptText: String, button label
- btnDeclineText: String, button label
- accept: function, callback to handle accept
- decline: function, callback to handle decline
- popped: Boolean, set this property in your localstorage to track if cookie has been shown for the user
- linkUrl: String, a url
- linkText: String, the text to display for the link
- type: 'top', 'bottom', or 'modal'

### localStorage
 - cookieHasPopped: cookie has been shown


## NetworkUtils (by Anton) - ALPHA - Handles your Fetch calls like a boss.

### use
In your root component:
```js
import { NetworkUtils } from 'samjs-components'
...
NetworkUtils.get(myRoute, myExtraHeaders).then(() => {
  //Do awesome stuff
});
...
```
### params
- route: API endpoint (e.g.: 'users/login')
- extraHeaders: an array of headers you want to include
- body: the body of your request

### methods
- get: route string, array of headers
- post: route string, body, array of headers
- put: route string, body, array of headers
- delete: route string

### session handling for OAuth
You should have your OAuth token available in localStorage with the key 'session'.
 ```js
...
localStorage.setItem('session', '<myToken>');
...
```

### define your API host
Set your API host in your env file as 'REACT_APP_API_HOST'.
This enables you to easily switch between environements without having to change any params for the NetworkUtils module.
