Examples List
============

This directory contains the following schemas which are valid against the schema version indicated by its name.

Requests
========

request-basic.json
----------

A booking request for a single unescorted traveller.

* Non-complex
* Instruction to not wait for escort details
* Departure date after and arrival time constraints
* Departure airport specified using free text description, destination using IATA code
* No specified flight ticket constraints
* Travel doc type provided
* No special assistance or meal requirements

request-basic-superseding-earlier-request.json
-------------------------

Demonstrates what would be sent if the requirements for a request change. Example is an amendment on request-basic.json.

* This subsequent message contains a new request Id.
* The traveller on the booking contains the same person Id as the orignal request (it's the same person).
* The person details indicate that their inclusion on this request supersede the earlier request i..e no further work should be done for that person in relation to the earlier request.
* The only change is that the earliest travel date has been pushed back by 2 days.

request-escorted-single.json
--------------------

As basic.json but with need for medical and security escort.

* Request states that TSP should wait for escort details before making booking.
* Traveller details indicate both medical and security escorts are needed.

request-family-complex.json
-------------------

A family group consisting of an adult female and dependant male child.

* Complex flag set with reason provided
* Request states that TSP should wait for escort details before making booking
* Departure and destination airports specified using IATA codes
* Depart date must be before constraint
* Flight ticket constraints are specified - a particular flight number, routing requirements and refundable tickets required
* Travel document information not available
* Son requires medical escort
* travellers[1] is dependent on travellers[0]
* Both travellers have meal requirements
* traveller[1] has special assistance requirements


Responses
=========

response.json

An example response message. All response messages have the same structure.
