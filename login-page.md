There is a problem with login screen in sustain online project. A user has the login credentials stored in google chrome auto complete. when such user tries to login to the platform, the form is filled during the page load. In such scenarios the login button is disabled to the users even if the credentials entered in the input fields are valid.

![login button disabled after the page loaded with form data](/images/disabled-login.png)

The button is disabled for invalid inputs and the fields are considered invalid on the first load with no input. Due the fileds of the login form being auto filled during the pageload, the validation on input fields is not happening. Google chrome is not dispatching the change event for the autofilled forms. However, when a user interacts with the page by clicking anywhere in the page, the login button is enabled back.

![login button enabled after the click interaction](/images/login-enabled-after-interaction.png)

### Input field inspected in dev-tools

![input filed highlighted in dev tools](/images/disabled-login-dev-tools.png)

### Solutions attempted:

- Focus on the inputs after the page in componentDidMount.
- Use settimeout to simulate click on the body after some delay.
- Use settimeout to bring focus to the body

### Links Referred

- [Stackoverflow answer](https://stackoverflow.com/questions/11708092/detecting-browser-autofill)
- [Blog Post](https://avernet.blogspot.com/2010/11/autocomplete-and-javascript-change.html)
