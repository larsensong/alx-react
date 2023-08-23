# 0x07-react_redux_action_creator_normalizr

0. Read data from a JSON
Reuse the latest dashboard project you worked on in the React course 0x06-React_state

For this task, place notifications.json into the root of the project directory and use the data inside for the next step.

Create a new notifications.js file in a schema folder:

Import the JSON data from notifications.json and give it a name. Try import * as [variable name] from [path to notifications.json]
Create a function named getAllNotificationsByUser that accepts userId as an argument
The function should return a list containing all the context objects from the notifications.json data when the author id is the same as the userId
In the same schema directory, create a notifications.test.js file:

Add a test that uses the id 5debd764a7c57c7839d722e9 and verifies that the following data is returned:

1. Normalize a nested JSON

Copy over dashboard from the previous task into a task_1 directory at the root of the project

Modify src/schema/notifications.js to set up a schema using Normalizr

You’re going to use schema.Entity to create a 3 of entities.

The first one is an example the task will provide for you.

const user = new schema.Entity("users")

Create a message entity in a variable called message whose key is messages and set the idAttribute to the string guid in the options
Create a notification entity in a variable called notification whose key is notifications and set the definition of the entity as so:
author: user
context: message
Add a test in schema/notifications.test.js to verify that your normalized data has a correct result array. It should contain:

Add a test to verify that your normalized data has a correct users entity. Test to access the user with the id 5debd764a7c57c7839d722e9. It should return:

      age: 25,
      email: "poole.sanders@holberton.nz",
      id: "5debd764a7c57c7839d722e9",
      name: { first: "Poole", last: "Sanders" },
      picture: "http://placehold.it/32x32"
Add a test to verify that your normalized data has a correct messages entity. Test to access the message with the guid efb6c485-00f7-4fdf-97cc-5e12d14d6c41. It should return:

      guid: "efb6c485-00f7-4fdf-97cc-5e12d14d6c41",
      isRead: false,
      type: "default",
      value: "Cursus risus at ultrices mi."
Add a test to verify that your normalized data has a correct notifications entity. Test to access the notification with the id 5debd7642e815cd350407777. It should return:

      author: "5debd764f8452ef92346c772",
      context: "3068c575-d619-40af-bf12-dece1ee18dd3",
      id: "5debd7642e815cd350407777"
Tips:

The expected goal is to obtain a very easy to use dataset
If you are having undefined issues, look at idAttribute from the Normalizr documentation
Requirements:

You must export the list of notifications using a Normalizr’s normalize
All the tests in the project should pass
