# jb-ticket-merge
Copyright (C) 2019-2020 Jeffrey Bostoen

[![License](https://img.shields.io/github/license/jbostoen/iTop-custom-extensions)](https://github.com/jbostoen/iTop-custom-extensions/blob/master/license.md)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/jbostoen)
🍻 ☕

Need assistance with iTop or one of its extensions?  
Need custom development?  
Please get in touch to discuss the terms: **jbostoen.itop@outlook.com**

## What?
Merges any sub class of Tickets.

One Ticket is chosen as "target" Ticket. The user decides which ticket will be kept as main Ticket, and which ones will be merged.

The attribute types to be merged are:
* ```AttributeCaseLog```
  Merges case log entries (sorted chronologically!). 
  There's an option to append/prepend a new log entry.
* ```AttributeLinkedSet```
  Related work orders, ...
* ```AttributeLinkedSetIndirect```  
  Related functional CIs, functional Contacts, ...

Attachments may be copied to the target Ticket.

**Options**

* specify which attributes can be merged, which ones are merged by default, which ones are always merged (forced), ...

* add callers from merged Tickets on the related contacts tab of the target Ticket. This allows Notifications to be sent to everyone linked to this Ticket.
* add description from merged Tickets as a case log entry (for example in public_log).

* New triggers
  * Trigger On Ticket Merge Source Processed
    * Offers access to information about this one source Ticket (excludes target Ticket!)
    * Placeholders: current_contact_id, current_contact_friendlyname, current_date, current_time and target_object
    * Use case: inform the caller of the source Tickets that their Ticket has been merged with the target Ticket (and give that Ticket's reference)
  * Trigger On Ticket Merge Target Processed
    * Offers acces to information about the target Ticket only
    * Placeholders: current_contact_id, current_contact_friendlyname, current_date, current_time
    * Use case: notify caller and now related contacts on target Ticket that Tickets have been merged and others will now receive notifications too.

**Work in progress*

* perform actions on target object as well as merged objects, similar to Combodo's User Actions Configurator.
  * on all objects: apply stimulus (so they can be resolved/closed automatically), set attributes, append log entries, ...
  * retrofit from target object to merged objects: copy (attributes), copy_head (most recent case log entry)


## Out of scope
Ideas which will only get implemented when sponsored:
* merge Tickets into new Ticket instead of existing one
* merge different child classes of Tickets into one
* detailed history track (which log entries, linked sets, attachments, ... were merged and from which original Ticket?)

## Screenshots

This shows the entire process.

First ticket
![Step 0](screenshots/20190815_step_0_ticket1.PNG)

Second ticket
![Step 0](screenshots/20190815_step_0_ticket2.PNG)

Lists now have a "merge" menu item.
![Merge menu item](screenshots/20190815_step_1_list_merge_menu.PNG)

Confirming selection of tickets
![Confirming selection of tickets](screenshots/20190815_step_2_confirm_selection.PNG)

Confirming attributes and target ticket
![Confirming attributes and target ticket](screenshots/20190815_step_3_confirm_attributes_and_target.PNG)

Result
![Result](screenshots/20190815_result_ticket.PNG)

Resulting history
![Result history](screenshots/20190815_result_ticket_history.PNG)


## Cookbook

XML:
* something

PHP:
* how to introduce custom iTop pages
* how to add a menu item in the Other Actions menu
* how to add custom triggers (Action and EventNotification)
* use built-in iTop methods to obtain attribute list for a class
* use built-in iTop methods to display lists
* use built-in iTop methods to check user rights
* use built-in iTop methods to prevent malicious actions
* use built in iTop methods to uniquely identify objects or look for very similar ones or see if attributes changed
* ...

