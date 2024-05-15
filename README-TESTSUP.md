## JOUR 3

### 1 ) (1 point) Create FUNCTIONAL test:
- On success with expect 200 statues 
  - On success with expect payload output 
- On success on endpoint ```/healt``` with 204 status code without response content
- On error with expect 404 status 
  - On error with expect payload error message. Payload message error structure is ```{‘message’: ´string’}```
- On success with expect 403 forbidden status code


### 2 ) (1 point) Create or update all your unit test 
- for the previous with this prototype format: ```test[nomMethode][cas][resultat/comportementAttendu]()```;


### 3 ) (1 point) Push report covering 
- of the unit test in codecov (level: easy)


### 4 ) (1 point) Create mock 
- for mongodb client  (point bonus individuel possible) (level: no easy because High cost/effort)


### 5 ) (1 point) Create stress test 
- with JMeter and push the report on Latency Lingo (level: no easy because High cost/effort)


### 6 ) (1 point) Add all test 
- in github action

### Bonus 
(1 point)  Up to date your documentation (for secure access + github action + cloud function)
