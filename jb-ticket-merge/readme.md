# jb-ticket-merge

Copyright (C) 2019-2021 Jeffrey Bostoen

[![License](https://img.shields.io/github/license/jbostoen/iTop-custom-extensions)](https://github.com/jbostoen/iTop-custom-extensions/blob/master/license.md)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/jbostoen)
🍻 ☕

Need assistance with iTop or one of its extensions?  
Need custom development?  
Please get in touch to discuss the terms: **info@jeffreybostoen.be** / https://jeffreybostoen.be

## Video presentation

* https://youtu.be/2_kujS5b15k


## What?


### Summary

Merges any sub class of Tickets.

One Ticket is chosen as **"target" ticket**.  
The agent decides which ticket will be kept as main ticket and which ones will be merged into the main ticket.  

The attribute types to be merged are:
* **AttributeCaseLog** - merges case log entries (sorted chronologically!) + possible append/prepend
* **AttributeLinkedSet** - related work orders, ...
* **AttributeLinkedSetIndirect** - related functional CIs, functional contacts, ...

Attachments may be copied to the target ticket.


### Options

* specify which attributes can be merged, which ones are merged by default, which ones are always merged (forced), ...
* add callers from merged tickets on the related contacts tab of the target ticket. 
  * Use case: this allows Notifications to be sent to everyone linked to this Ticket.
* add description from merged tickets as a case log entry (for example in public_log).
* optional: automatically delete the tickets which were merged

### New triggers

**Trigger On Ticket Merge Source Processed**
  * Offers access to information about this one source Ticket (excludes target Ticket!)
  * Placeholders: current_contact_id, current_contact_friendlyname, current_date, current_time and target_object
  * Use case: inform the caller of the source Tickets that their Ticket has been merged with the target Ticket (and give that Ticket's reference)
  
**Trigger On Ticket Merge Target Processed**
  * Offers acces to information about the target Ticket only
  * Placeholders: current_contact_id, current_contact_friendlyname, current_date, current_time
  * Use case: notify caller and now related contacts on target Ticket that Tickets have been merged and others will now receive notifications too.

### Work in progress

* perform actions on target object as well as merged objects, similar to Combodo's User Actions Configurator.
  * on all objects: apply stimulus (so they can be resolved/closed automatically), set attributes, append log entries, ...
  * retrofit from target object to merged objects: copy (attributes), copy_head (most recent case log entry)

## Out of scope

These are some ideas which will only get implemented after sponsoring these features:

* merge Tickets into new Ticket instead of existing one
* merge different child classes of Tickets into one
* detailed history track (which log entries, linked sets, attachments, ... were merged and from which original Ticket?)

## Requirements

* iTop extensions
  * [jb-framework](https://github.com/jbostoen/itop-jb-framework) - a generic framework shared among some of my extensions



## Screenshots

Initial ticket A  
![Step 0](screenshots/20190815_step_0_ticket1.PNG)

Initial ticket B  
![Step 0](screenshots/20190815_step_0_ticket2.PNG)

At least two (or more) tickets should be selected in a list overview.  
Then the **Merge** action can be used.  
![Step 1](screenshots/20190815_step_1_list_merge_menu.PNG)

The selection has to be confirmed.  
![Step 2](screenshots/20190815_step_2_confirm_selection.PNG)

A basic overview allows the agent to choose the target ticket and which info has to be merged.  
![Step 3](screenshots/20190815_step_3_confirm_attributes_and_target.PNG)

The resulting ticket in this example contains all info from both tickets.  
![Result](screenshots/20190815_result_ticket.PNG)

This action is also logged in the history of the ticket.  
![Result history](screenshots/20190815_result_ticket_history.PNG)

## Cookbook

PHP:
* how to show custom iTop pages
* how to add a menu item in the Other Actions menu
* how to add custom triggers (Action and EventNotification)
* use built-in iTop methods to obtain attribute list for a class
* use built-in iTop methods to display lists
* use built-in iTop methods to check user rights
* use built-in iTop methods to prevent malicious actions
* use DBObject::Fingerprint() for various tasks: to uniquely identify objects or look for very similar ones or see if attributes changed
* ...

