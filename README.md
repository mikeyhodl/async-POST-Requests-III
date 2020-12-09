# async-POST-Requests-III

async POST Requests III
Since you’ve created the boilerplate code for a POST request, the next step is to incorporate that experience and logic into making a real request.

In this exercise, you’ll need to retrieve your Rebrandly API key to access the Rebrandly API.

Rebrandly API Keys.
If you reset the exercise at any point, you will have to paste in your API key again at the top!

Instructions
1.
At the top of main.js, assign apiKey to your Rebrandly API key.

2.
Under the comment “AJAX functions”, create a new arrow function and assign it to a const shortenUrl() using the async keyword.


Hint
The syntax will look like:

const shortenUrl = async () => {}
3.
Inside the code block of the arrow function of shortenUrl create two consts:

One named urlToShorten and assign it inputField.value.

The other named data and assign it the value of calling JSON.stringify() and passing in {destination: urlToShorten}.

Please note, we will be working inside shortenUrl() for the remainder of the exercise.

4.
Add a try statement and leave the code block empty for now. After the try code block, create a catch statement and pass in error.

In the code block of catch(error), log error to the console.


Hint
The syntax will look something like:

try {
  // Empty for now
} catch (error)  {
  console.log(error)
}
5.
Inside the try code block, using const, create a variable named response and assign it to await the value of calling calling fetch().


Hint
Break this step into smaller bits. “using const, create a variable named response“

const response 
“assign it to await the value of calling calling fetch()“

const response = await fetch();
6.
In the fetch() call, pass in url as the first argument and an empty object as the second argument.

In that empty object you just created. It will have the following three properties:

method with a value of 'POST'
body with a value of data
headers with a value of the object below:
{
'Content-type': 'application/json',
'apikey': apiKey
}

Hint
Remember to separate your properties using commas!

The basic structure of the object will look like:

{
  key1: value1,
  key2: value2,
  key3: {
    'Content-type’: 'application/json’,
    'apikey': apiKey
  }
}
7.
Below the variable response from the previous step, create a conditional statement that the checks if the ok property of response evaluates to a truthy value.


Hint
Make sure you’re not inside the code block of the 2nd argument for fetch(). This step is asking you to use an if statement to check response.ok The general syntax will look like:

const response = await fetch(/*Code for fetch*/)
if(response.ok){}
8.
Inside the code block of the conditional statement, await response.json() and save it to a variable called jsonResponse using the const keyword.

9.
Call the function renderRawResponse() and pass in jsonResponse. Then, run the code.

In the response field, you can paste in a URL and click the shorten button.

You should now see an object containing all the information the Rebrandly API sent back!

You can view the purpose of the renderRawResponse() helper function at public/helperFunctions.js.

10.
Now it’s time to clean up the response sent back.

Delete renderRawResponse(jsonResponse) and replace it with renderResponse(jsonResponse). Run the code. Then paste in the URL again and click the shorten button.

Notice the formatted response.

Great job using Rebrandly to shorten your URL!

You can view the purpose of the renderRawResponse() helper function at public/helperFunctions.js.
