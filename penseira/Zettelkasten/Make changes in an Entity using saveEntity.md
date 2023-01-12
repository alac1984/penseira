04/01/2023 12:51

Status: #walkthrough #canBeImproved 

Tags: [[Bizagi]] [[SOAPUi]] [[Bizagi's SOA Layer]]

This steps were written considering this operation happening in a on premise system in my own laptop:

1. Open Bizagi Studio
2. Choose the Project you want to open
3. Run the project for web server start
4. Open SOAPUi and create a project like [[Create SOAPUi Project]]
5. In Bizagi, open Model Data to get entity's names
6. Using getEntities like in [[getEntities]], get entity's nodes. We can find the `getEntities` endpoint example in SOAPUi navigation bar, and start from there.
7. Using saveEntity like in [[saveEntity]], chosse an attribute to change and make the request. We can find the `saveEntity` endpoint example in SOAPUi navigation bar, and start from there.

## Improvement Notes

In 3, does we really need to run a process for Bizagi's web server start serving it?


---
# References

[[MeDoingThingsByMyself]]