# 32
The first line indicates that you're creating a key for a form. In our context, it is the login form. You're creating it to identify the form uniquely. It is set to final, so that it won't change.

# 33 34
The next 2 lines are definitions of controllers. A controller in our context is used to read the values from the input. Using a controller, you'll be able to control its associated component.

# 37
Let's dismantle the build method. You use the build method in Flutter to build the UI. It contains the design code. The content returned from this method will be rendered on the UI.

# 38
The Scaffold is a widget in Flutter used to implement the basic material design visual layout structure. Assume the widget is a simple UI component.

We're setting the title passed as a parameter to this class. We can access the parameters using the widget object. So, it goes like widget.{key_name}.

If you want to access the title property, then it'll be widget.title. This is similar to passing props in React.

# 42
The next section is body. As we're building a simple login app, we need a form to be filled out by the user to authenticate. 

# 43
We're setting the unique key which we created above to this form. 

# 44
The Form accepts a child. It can accept only one component.

# 45
We are creating a layout with horizontal padding of 8px and vertical padding of 16px. 

# 46
This Padding widget also accepts only one child.

# 47
Column is a widget in Flutter that is used to display its children in a vertical array. We set crossAxisAlignment to horizontally center the contents of the Column widget.

# 48
As we saw, the Column widget displays its children in a vertical array. We can pass multiple widgets in its children property.

# 49 52 53
The first item we want to display in the UI is an input box to get the email address of a user. So, we used the TextFormField widget and set the controller to emailController.

# 54 55
In order to get the floating text, we need to use the decoration option which asks for the type of border and the labelText of the input.

# 56 - 63
We can add any default validation to be applied when this form is submitted in the validator field. We're validating if it's either a null or empty value and we return an error if any of them match. If it has some value, then we're not throwing any errors and returning null.

# 64 - 67
The second item is the input box to get the Password from the user. This is similar to the email field except for one thing: we should hide the password in the input field and display a dot for each typed character.

# 68 - 79
To do that, we have to pass an obscureText property to the TextFormField widget and set it to true. The decoration, validation, and other items remain the same as that of Email.

# 80
This is the final piece of our form, which is a submit button. 

# 84
We're using a ElevatedButton widget and passing the button text in the child property of the button. 

# 85
We define the action that should be followed when pressing this button in the onPressed property.

In our case, we're validating the input fields (remember the validator property we defined for the email and the password input box). 

# 86 87
If the validation passes, we should navigate the user to the next screen (which we'll be adding later). 

# 88 - 91
If not, we show a message asking the user to fill in the inputs ("Please fill input").



If you're facing any errors in viewing the UI, most of the time (almost 90%) it'll be with brackets. We'll be using a lot of brackets in Flutter which is often confusing for beginners. Make sure you have the proper opening and closing brackets. The Flutter app may terminate in the middle in case of any errors. In these cases, after applying the fix, press F5 to restart the app.