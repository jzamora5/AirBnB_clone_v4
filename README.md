# AirBnB Clone V4

This is a complete full-stack web application, integrating a MySQL database and Flask RESTful API with a dynamic HTML5/CSS3/jQuery front-end.

It was based off the basic characteristics of the Airbnb platform.

![](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step5.png)

![](https://holbertonintranet.s3.amazonaws.com/uploads/medias/2020/9/b68cd1e385963da099899f51ee5f3a6bbf0adcb3.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUWMNL5ANN%2F20210212%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210212T154046Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=2192a69138326bc86eb69e6d996051e4c1d9825876e57938110a2ab4a058d589)

# Iterations

The project was developed in several iterations, being V4 the last one. This iterations encompassed several concepts and integrations that will be explained below.

## The Console

The first iteration of the project consisted on building an interactive console in order to allow for development testing.

![The Console](https://holbertonintranet.s3.amazonaws.com/uploads/medias/2018/6/815046647d23428a14ca.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUWMNL5ANN%2F20210212%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210212T152825Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=36a670976b542ba984bb85e6e78ee7a9be0db662c4c2294318085d5b831e6cb9)

The Console was coded in order to work with a temporary storage engine based on JSON, and included the next features:

- Create a new object (ex: a new User or a new Place)
- Retrieve an object from a file, a database etc…
- Do operations on objects (count, compute stats, etc…)
- Update attributes of an object
- Destroy an object

The console has 2 modes.

**Interactive**

```
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
```

**Non Interactive**

```
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```

## Web Static

This part of the project consisted in building the basic CSS and HTML source code.

![](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step1.png)

![](https://holbertonintranet.s3.amazonaws.com/uploads/medias/2020/9/f47a405fccad371100ff9665dae9b3a84a471e62.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUWMNL5ANN%2F20210212%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210212T154740Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=a1413640abe6e2e40586c00d2d77446b0f066207c2af1ad960cb1cd208ef411a)

## MySQL

This section consisted on the data modeling for the relational database in MySQL.

![](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step2.png)

![](https://holbertonintranet.s3.amazonaws.com/uploads/medias/2020/9/daaef631636b40e0a279a8f240703e065f9d3481.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUWMNL5ANN%2F20210212%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210212T155037Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=c111856c357a312c3cf31f1113735711c877e7b6b29817420d241a59024a4d7f)

## Web Framework

This iteration consisted on building the first approach to dynamic content for the application by using Flask and Jinja, and effectively having Server Side Render.

For this development, the MySQL database started being used in order to serve content to the client, and provide it with back end based features.

All of the HTML and CSS source code started being hosted in the server, and no items were hard coded, but instead produced through dynamic data integration.

![](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step3.png)

![](https://holbertonintranet.s3.amazonaws.com/uploads/medias/2020/9/bf248a63c15a746ad694acffdd56d80281782c71.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUWMNL5ANN%2F20210212%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210212T155137Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=9db02fb354e84f26b389b98bd448812bc0e1276ed11239c3ff1506a123008f08)

## RESTful API

Although the Server Side Render with Flask and Jinja was interesting, this section consisted on developing a different approach to dynamic content generation, starting with a RESTful API.

This Application Programming Interface was built with Flask and SQLAlchemy in order to work with MySQL and respond to HTTP requests.

![](https://holbertonintranet.s3.amazonaws.com/uploads/medias/2020/9/02078cd7f0573885c85a225c7436584a5afea1f9.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARDDGGGOUWMNL5ANN%2F20210212%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210212T155744Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=ca7db9cb54ede7b9854b2f022e2de0df562885e0936873925eb49e129f634b4b)

The endpoints can be seen below.

    GET /api/v1/status
    **Returns the status of the API

    GET /api/v1/stats
    **Retrieves the number of each objects by type
    GET /api/v1/states
    **Retrieves the list of all State objects

    GET /api/v1/states/<state_id>
    **Retrieves a State object
    DELETE /api/v1/states/<state_id>
    **Deletes a State object
    POST /api/v1/states
    **Creates a State
    PUT /api/v1/states/<state_id>
    **Updates a State object

    GET /api/v1/states/<state_id>/cities
    **Retrieves the list of all City objects of a State
    GET /api/v1/cities/<city_id>
    **Retrieves a City object
    DELETE /api/v1/cities/<city_id>
    Deletes a City object
    POST /api/v1/states/<state_id>/cities
    Creates a City
    PUT /api/v1/cities/<city_id>
    Updates a City object

    GET /api/v1/amenities
    **Retrieves the list of all Amenity objects
    GET /api/v1/amenities/<amenity_id>
    **Retrieves a Amenity object
    DELETE /api/v1/amenities/<amenity_id>
    **Deletes a `menity object
    POST /api/v1/amenities
    **Creates a Amenity
    PUT /api/v1/amenities/<amenity_id>
    **Updates a Amenity object

    GET /api/v1/users
    **Retrieves the list of all User objects
    GET /api/v1/users/<user_id>
    **Retrieves a User object
    DELETE /api/v1/users/<user_id>
    **Deletes a User object
    POST /api/v1/users
    **Creates a User
    PUT /api/v1/users/<user_id>
    **Updates a User object

    GET /api/v1/cities/<city_id>/places
    **Retrieves the list of all Place objects of a City
    GET /api/v1/places/<place_id>
    **Retrieves a Place object
    DELETE /api/v1/places/<place_id>
    **Deletes a Place object
    POST /api/v1/cities/<city_id>/places
    **Creates a Place
    PUT /api/v1/places/<place_id>
    **Updates a Place object

    GET /api/v1/places/<place_id>/reviews
    **Retrieves the list of all Review objects of a Place
    GET /api/v1/reviews/<review_id>
    **Retrieves a Review object
    DELETE /api/v1/reviews/<review_id>
    **Deletes a Review object
    POST /api/v1/places/<place_id>/reviews
    **Creates a Review
    PUT /api/v1/reviews/<review_id>
    **Updates a Review object

    GET /api/v1/places/<place_id>/amenities
    **Retrieves the list of all Amenity objects of a Place
    DELETE /api/v1/places/<place_id>/amenities/<amenity_id>
    **Deletes a Amenity` object to a Place
    POST /api/v1/places/<place_id>/amenities/<amenity_id>
    **Link a Amenity object to a Place

    POST /api/v1/places_search
    **Retrieves all Place objects depending of the JSON in the body of the request.

    GET /apidocs
    **Gets the documentation of the API built in Flasgger

## Web Dynamic

This was the final iteration of the project and consisted in changing the Server Side Render for Client Based Render using JavaScript with JQuery, and the RESTful API from before.

![Image result for jquery and javascript](https://miro.medium.com/max/600/1*8Whvj5G9f5DVmCBIzywYww.png)

![](https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step5.png)

# Challenges and Future Features

This was a big project that helped in understanding how a Fullstack application works. Some of the most challenging parts had to do with the Object Relational Mapping for the API, and the Client Based Render.

For future projects, this serves as a great base for beginning to understand other technologies such as React, NodeJS, and Mongo, among others.

# About Myself

🎯 I am a Fullstack developer in love with technology and keen to learn new things everyday. My strenghts reside in Python and JavaScript although I am not afraid to take on any other language.

🎯 I have experience developing both back end and front end. I have used technologies such as Bootstrap, SASS, React, Flask, Django, Express, SQL, MongoDB, AWS, among others.

🎯 I also studied Sound Engineering some years ago, and I love music, videogames, and audiovisual media.

🔹 [LinkedIn](https://www.linkedin.com/in/jhoan-stiven-zamora-caicedo/)
🔹 [Twitter](https://twitter.com/JhoanZamora10)
