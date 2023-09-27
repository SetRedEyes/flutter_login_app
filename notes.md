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

# 111 - 112
In this code, we are creating a new class called "HomePage" and extending it from "StatelessWidget". We receive an email from the previous page.

# 117 - 136
On the build method, we define the title of the page to be "Home Page" and its body contains a Text and ElevatedButton widget. The Text widget will display the email address passed from the previous screen. The ElevatedButton widget will navigate the user to the previous screen whenever it's pressed. We use Navigator.pop(context); to navigate to the previous screen.



# final
The final keyword in Dart is used to create constants or objects that are immutable in nature. The only difference between the final and const keyword is that final is a runtime-constant, which in turn means that its value can be assigned at runtime instead of the compile-time that we had for the const keyword.

# final vs const

Final:

"final" means single-assignment: a final variable or field must have an initializer. Once assigned a value, a final variable's value cannot be changed. final modifies variables.

Const:

"const" has a meaning that's a bit more complex and subtle in Dart. const modifies values. You can use it when creating collections, like const [1, 2, 3], and when constructing objects (instead of new) like const Point(2, 3). Here, const means that the object's entire deep state can be determined entirely at compile time and that the object will be frozen and completely immutable.

Const objects have a couple of interesting properties and restrictions:

They must be created from data that can be calculated at compile time. A const object does not have access to anything you would need to calculate at runtime. 1 + 2 is a valid const expression, but new DateTime.now() is not.

They are deeply, transitively immutable. If you have a final field containing a collection, that collection can still be mutable. If you have a const collection, everything in it must also be const, recursively.

They are canonicalized. This is sort of like string interning: for any given const value, a single const object will be created and re-used no matter how many times the const expression(s) are evaluated.

So, what does this mean?
Const:
If the value you have is computed at runtime (new DateTime.now(), for example), you can not use a const for it. However, if the value is known at compile time (const a = 1;), then you should use const over final. There are 2 other large differences between const and final. Firstly, if you're using const inside a class, you have to declare it as static const rather than just const. Secondly, if you have a const collection, everything inside of that is in const. If you have a final collection, everything inside of that is not final.

Final:
final should be used over const if you don't know the value at compile time, and it will be calculated/grabbed at runtime. If you want an HTTP response that can't be changed, if you want to get something from a database, or if you want to read from a local file, use final. Anything that isn't known at compile time should be final over const.

With all of that being said, both const and final cannot be reassigned, but fields in a final object, as long as they aren't const or final themselves, can be reassigned (unlike const).