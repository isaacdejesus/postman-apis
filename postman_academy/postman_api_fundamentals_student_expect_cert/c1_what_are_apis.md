# Application Programming Interfaces
- Application Programming Interfaces (API) is a contract that allows code to talk to other code. APIs allow sharing 
  of resources and services across apps, orgs and devices.
## Wy are APIs important?
1. APIs help devs integrate features and build automation w/out reinventing the wheel.
    - Ex. Using Weather API instead of launching weather balloons
2. APIs allow enterprises to open their product for faster innovation
    - Ex. Apps that interact with twitter/meta APIs by posting on your behalf
3. APIs can be products 
    - Ex. Software as a service (SaaS) like stripe payment API or twilio's text msg and email APIs
# APIs - A digital restaurant
- Think of APIs like a waiter at a restaurant, serving as a go-between for customer and kitchen
    - Client/Customer: Is the requester, can be browser, web app, mobile app. 
    - API/Waiter: Is simplified interface for interacting with backend
    - Server/Kitchen: Is backend where processing happens
# Types of APIs
- Couse focuses on Web APIs, however API applies to a broad range of interfaces
    - Hardware APIs: Interface for software to talk to hardware
        - Ex. Phone cam talking to OS
    - Software Lib APIs: Interface for consuming code from anoter code base
        - Ex. Using methods from lib to import into your app
    - Web APIs: Interface for communicating across code bases over a network
- Multiple API types can be used to achieve a task: Ex. Uploading photo to instagram uses various APIs
    - Hardware API for app to talk to camera
    - Software lib API for img to be processed with filters
    - Web API for sending img to instagram servers to be viewed by ppl
- Architectures: There are more than one way to build and consume APIs
    - REST(Representational State Transfer)
    - GraphQL
    - WebSockets
    - webhooks
    - SOAP(Simple Object Access Protocol)
    - gRPC(Google Remote Procedure Call)
    - MQTT(MQ Telemetry Transport)
- Course will focus on REST APIs
- REST APIs: Some traits of REST APIs include not storing session state between requests, ability to cache, ability to send
  and recieve various data types.
- Access: APIs vary in the scope of who can access them
    - Public APIs(Open APIs): Consumed by anyone who discovers the API
    - Private APIs: Consumed only within org and not made public
    - Partner APIs: Consumed between 1+ orgs that have a relationship
- https://blog.postman.com/different-types-of-apis/
