Instructions:

- Add your answers inline to the markdown file.
- Use your own words.
- Come up with an answer from memory. Write it down, even if the answer is "I don't know."
- Then, we will go over the answers in class. Write down your revised answer below your original answer.
- There are two intermissions. We will go over the answers to the previous parts during those times.
- Finally, submit all of your answers in a file to canvas. This is so Lloyd and I can get a sense of your understanding.

---
### Part 1: Servers - 20 minutes

1. What is a server? What does a server do?

It is a computer which provides web pages and applications to a client (e.g. a user accessing web pages through the browser.)

2. What is Node.js?

Node.js is a library or framework which is based on JavaScript. It allows us to use JavaScript for backend programming (making http requests and responses.)

3. What is express?

Express is a package which allows you to use your computer as a server.

4. What is a client? What does a client do?

A client makes requests to the server to access web pages or applications.

5. How do the server and the client communicate?

Through http requests and responses.

6. Debugging:
- 6a. How do you view server logs?

Through middle ware such as Morgan, or through console.log statements within your code.

- 6b. How do you view client logs?

Right click > Inspect > Network
---
### Part 2: HTTP Requests - 15 minutes

1. What is an HTTP Request?

A request from the client to the server to access a web page.

2. GET Requests
- 2a. What is a GET request?
- 2b. When do you use GET requests?
- 2c. How do you send data in a GET request?

3. POST Requests
- 3a. What is a POST request?


- 3b. When do you use POST requests?


- 3c. How do you send data in a POST request?

---

### Intermission

---
### Part 3: Ajax - 15 minutes

1. Ajax
- 1a. What is Ajax?

Asynchronous JavaScript and XML.

- 1b. When should you use Ajax?

To create a webpage which has updated content without refreshing the page.

2. Given the following code snippet:

```js
console.log("A");
$('#map').click(function(event) {
	console.log("B");
	var coordinates = convertMouseCoordinatesToGeoCoordinates(event);

	console.log("C");
	$.get('/map', { lat: coordinates.x, lon: coordinates.y }, function(response, status) {
		console.log("D");
		mapDisplay.update(response);
	});

	console.log("E");
});
console.log("F");
```

- 2a. Describe what seems to be happening.

1. "A" is logged to the console.
2. When the element with id map is clicked,
		a) "B" is logged to the console.
		b) "C" is logged to the console.
		c) A get request is initiated to url: /map
		d) 	- wrapped in an object is coordinates called to x and to y.
		    - "D" is logged to the console.
				- call update function on mapDisplay
		e) "E" is logged to the console.
3. "F" is logged to the console.

- 2b. In what order is `A` through `F` printed?
- 2c. Describe the events that happen between each letter. When does the server get hit?

---

### Intermission

---
### Part 4: Jade - 20 minutes

1. Jade
- 1a. What is Jade?

(Pug) is a templating language used to render html.

- 1b. Why should we use Jade?

In order to write DRY code (e.g. content that remains the same across many pages of a website or app - the nav bar, side bar, styling etc. should be edited it 1 file. )

2. Explain the difference between 'server side' JavaScript and 'client side' JavaScript.

Client side refers to the front end, user interactions etc. (JQuery event handlers) and server side refers to backend side, http requests.

3. Given this example `index.jade` file:

```js
doctype html
html
	head
		script(src='boop.js')
		script.
			var x = 1;
	body
		- var y = 2;
		h2= z + y
```

- 3a. Is `x` executed server side or client side? Does the client ever see `x`?

client side, but the client only sees h2

- 3b. Is `y` executed server side or client side? Does the client ever see `y`?
- 3c. Is `z` executed server side or client side? Does the client ever see `z`?
- 3d. When is `boop.js` executed? Does the client ever see `boop.js`?

---
### Part 5: Request Lifecycle - 15 minutes

5. Given the following code snippet in an express application:

```js
app.get('/home', function (request, response) {
	response.render('index', { z: 3 } );
});
```

- 5a. List the complete order of events, starting from the browser making a `GET` request to `/home`. Assume that `index` refers to the Jade file in Part 4. Be sure to describe when each JavaScript statement (`x`, `y`, `z`, and `boop.js`) gets executed.
- 5b. What is displayed on the page?
- 5c. What is visible from 'view page source'?
