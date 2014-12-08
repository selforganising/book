# Heroku

### What is it?

Heroku is a cloud platform as a service. It is not open source, however for our usage it will be free.


### Why use it?

What does ‘cloud platform as a service’ mean?  Basically rather then a developer having to build an infrastructure, manage their servers, deploy or scale, you can make all that simple by using heroku. 

| **Advantages**                                | **Disadvantages**                                 |
| ----------------------------------------------|--------------------------------------- -----------|
| Easy Setup                                    | Pricey will pay 3x - 5x more than competitors     |
| Easy to Scale Up                              | Not managing your own infrastructure              |
| Great plugin support for third party apps     | Lock-In - not easy to move to a competitor        |
| Free to start (first 750 computation hours)   | Single point of failure (rare, but possible)      |
| Instant Deployment with Git Push              |                                                   |


### Competitors:

* Windows Azure
* Amazon Web Services
* Google App Engine
* VMware
* HP Cloud Services
* Force.com
* IBM Smart Cloud
* Digital Ocean


### How to Setup:

1. Go onto Heroku and set up account
2. Install Heroku toolbelt (using brew install on a mac)
3. `git init` (or `git clone`)
4. `Heroku login` (created a ssh file)
5. Double check you have done that correctly by `Heroku keys`
6. `Heroku Create <name of project>`
7. `git heroku push master`
8. `heroku open`
9. `heroku ps: scale web=1`


### Key things to know:

* should have a package.json
* should have a procfile
* Portnumber needs to be `process.env.port`


### Resources:

* Offical Heroku/Node tutorial: https://devcenter.heroku.com/articles/getting-started-with-nodejs#introduction

* Beginners guide to Heroku/Node: http://niel.delarouviere.com/2012/03/the-really-absolute-beginners-guide-to-host-node-js-on-heroku/

* List of Competitors: https://www.g2crowd.com/products/heroku/competitors/alternatives
