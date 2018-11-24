## Challenge 1
Modified endpoint in app.py return single item instead of an array when retrieving a restaurant.

## Challenge 2
Implemented in Travis CI, passing tests with python 2.7 3.4 3.5 3.6

## Challenge 3
Using Alpine linux with Python 3.6.7 and the source code the image is 32.7MB and is published in [quay.io](https://quay.io/repository/paurosello/challenge?tab=info) with the Travis pipeline

## Challenge 4
I did not dockerize the database with the data inside (I consider this an antipattern), instead I created a Job that runs in a different container in order to seed the data.

## Challenge 5
Created the docker-compose file with the restaurant application, the mongo database and the seeding container that updates the data and finishes silently.

## Challenge 6
The following kubernetes resources are defined:
    - Restaurant Deployment
    - Restaurant Service (LoadBalancer)
    - Mongo Deployment
    - Mongo Service
    - Mongo Persistent Volume
    - Seeding Job

All these resources are deployed in a Kubernetes instance on GCE using the Travis pipeline.

The application can be accessed at [http://35.246.144.140/api/v1/restaurant](http://35.246.144.140/api/v1/restaurant)