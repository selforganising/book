#Acceptance Criteria

##Ron Jeffries 3 Cs

* **Card** – stories are traditionally written on notecards, and these cards can be annotated with extra details.
* **Conversation** – details behind the story come out through conversations with the Product Owner. 
* **Confirmation** – acceptance tests confirm the story is finished and working as intended.

###Card

* **User stories** - description of an objective a person should be able to achieve when using your website

As a *who*
I want *what*
So that *why*

For example:
“As a Flickr member I want to be able to assign different privacy levels to my photos so I can control who I share which photos with.”

###Converstation

* Meeting with product owner
* QA from discussing user stories

“As a Flickr member I want to be able to assign different privacy levels to my photos so I can control who I share which photos with.”

  * How many different privacy levels do they need?
  * Should changes apply to collections/individual photos?
  * Should they be sent a confirmation email?
  * What should the default setting be?

###Confirmation

* Acceptance criteria define the bounds of a user story and are used to confirm when a story is complete and working. 
* You demonstrate functionality by showing how each criterion raised in conversation is satisfied. 
* Form the tests 
* Remove ambiguity
* Encourage thinking from user perspective

###Product Backlog
* As mentioned above, the PO decides on the priority for all remaining work. This forms the “product backlog”. Items that are at the top of this queue will have a lot more detail than items towards the bottom. 
* There is little value adding a lot of detail to stories that are at the bottom of the backlog because a lot might change before you get around to working on them.

—> only need AC for working stories

###Definition of Done

*Unlike Conditions of Satisfaction, this is criteria that all stories must satisfy before they can be considered done.
*For example, the team might decide that every story should be code reviewed by at least two other people, must have undergone testing and must be merged to a specific place on the server.
*The team’s Definition of Done is usually printed out and placed near the Scrum board.
—> we can agree on definition of done

###Our Definition of Done Checklist

* Code reviewed by all remaining team members (we will be pair programming).
* Story code undergone satisfactory testing (reviewed by Tester).
* Final clearance from Will (PM) to merge pull request.
* Remote merging and deleting branch.

###Lessons

* Make sure you refer to different sections with different words, e.g. POI: category? subcategory? actual example?
* Get someone else to read it who has not written any AC. 
* Try to write in pairs.
