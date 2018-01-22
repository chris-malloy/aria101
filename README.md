# Aria 101

## Description
Introduction in Aria concepts and usage.

## Primary Documents
##### There are three primary documents that dictate how ARIA works and should be applied by developers.

### User Agent Implementation Guide

#### Live Examples

* [vertical](http://whatsock.com/tsg/Coding%20Arena/ARIA%20Menus/Vertical%20(Internal%20Content)/demo.htm)
* [horizontal](http://whatsock.com/tsg/Coding%20Arena/ARIA%20Menus/Horizontal%20(Internal%20Content)/demo.htm)

These Examples feature web application drop down menus that offer keyboard navigation properties that are idential to the right-click desktop drop down menu.

#### Important Terms 

##### Accessibility API
Operating systems and other platforms provide a set of interfaces that expose information about objects and events to assistive technologies. Assistive technologies use these interfaces to get information about and interact with those widgets. Examples of accessibility APIs are the Microsoft Active Accessibility [MSAA], the Microsoft User Interface Automation [UIA-ARIA], the Mac OS X Accessibility Protocol [AXAPI], the Linux/Unix Accessibility Toolkit [ATK] and Assistive Technology Service Provider Interface [AT-SPI], and IAccessible2 [IA2].

##### Accessibility Subtree
An accessible object in the accessibility tree and its descendants in that tree. It does not include objects which have relationships other than parent-child in that tree. For example, it does not include objects linked via aria-flowto unless those objects are also descendants in the accessibility tree.

##### Accessibility Tree
Tree of accessible objects that represents the structure of the user interface (UI). Each node in the accessibility tree represents an element in the UI as exposed through the accessibility API; for example, a push button, a check box, or container.

##### Accessible Name
The accessible name is the name of a user interface element. Each platform accessibility API provides the accessible name property. The value of the accessible name may be derived from a visible (e.g., the visible text on a button) or invisible (e.g., the text alternative that describes an icon) property of the user interface element.

A simple use for the accessible name property may be illustrated by an "OK" button. The text "OK" is the accessible name. When the button receives focus, assistive technologies may concatenate the platform's role description with the accessible name. For example, a screen reader may speak "push-button OK" or "OK button". The order of concatenation and specifics of the role description (e.g. "button", "push-button", "clickable button") are determined by platform accessibility APIs or assistive technologies.

##### Accessible object
A user interface object whose basic accessibility is exposed to assistive technology via a platform accessibility API. Accessible objects are included in the accessibility tree. MS UIA represents accessible objects as automation elements.

##### Assistive Technologies
Hardware and/or software that:

relies on services provided by a user agent to retrieve and render Web content
works with a user agent or web content itself through the use of APIs, and
provides services beyond those offered by the user agent to facilitate user interaction with web content by people with disabilities
This definition may differ from that used in other documents.

Examples of assistive technologies that are important in the context of this document include the following:

screen magnifiers, which are used to enlarge and improve the visual readability of rendered text and images;
screen readers, which are most-often used to convey information through synthesized speech or a refreshable Braille display;
text-to-speech software, which is used to convert text into synthetic speech;
speech recognition software, which is used to allow spoken control and dictation;
alternate input technologies (including head pointers, on-screen keyboards, single switches, and sip/puff devices), which are used to simulate the keyboard;
alternate pointing devices, which are used to simulate mouse pointing and clicking.
Attribute
In this specification, attribute is used as it is in markup languages. Attributes are structural features added to elements to provide information about the states and properties of the object represented by the element.

##### Class
A set of instance objects that share similar characteristics.

##### Desktop focus event
Event from/to the host operating system via the accessibility API, notifying of a change of input focus.

##### Element
In this specification, element is used as it is in markup languages. Elements are the structural elements in markup language that contains the data profile for objects.

##### Event
A programmatic message used to communicate discrete changes in the state of an object to other objects in a computational system. User input to a web page is commonly mediated through abstract events that describe the interaction and can provide notice of changes to the state of a document object. In some programming languages, events are more commonly known as notifications.

##### Hidden
Indicates that the element is not visible or perceivable to any user. An element is only considered hidden in the DOM if it or one of its ancestor elements has the aria-hidden (state) attribute set to true.

Note: Authors are reminded that visibility:hidden and display:none apply to all CSS media types; therefore, use of either will hide the content from assistive technologies that access the DOM through a rendering engine. However, in order to support assistive technologies that access the DOM directly, or other authoring techniques to visibly hide content (for example, opacity or off-screen positioning), authors need to ensure the aria-hidden attribute is always updated accordingly when an element is shown or hidden, unless the intent of using off-screen positioning is to make the content visible only to screen reader users and not others.

#####  Informative
Content provided for information purposes and not required for conformance. Content required for conformance is referred to as normative.

##### Keyboard Accessible
Accessible to the user using a keyboard or assistive technologies that mimic keyboard input, such as a sip and puff tube. References in this document relate to WCAG 2 Guideline 2.1; "Make all functionality available from a keyboard" [WCAG20].

##### Live Region
Live regions are perceivable regions of a web page that are typically updated as a result of an external event when user focus may be elsewhere. These regions are not always updated as result of a user interaction. This practice has become commonplace with the growing use of Ajax. Examples of live regions include a chat log, stock ticker, or a sport scoring section that updates periodically to reflect game statistics. Since these asynchronous areas are expected to update outside the user's area of focus, assistive technologies such as screen readers have either been unaware of their existence or unable to process them for the user. WAI-ARIA has provided a collection of properties that allow the author to identify these live regions and how to process them: aria-live, aria-relevant, aria-atomic, and aria-busy. Pre-defined live region roles are listed in the Choosing Between Special Case Live Regions ([ARIA-PRACTICES], Section 5.3).

##### Managed State
Accessibility API state that is controlled by the user agent, such as focus and selection. These are contrasted with "unmanaged states" that are typically controlled by the author. Nevertheless, authors can override some managed states, such as aria-posinset and aria-setsize. Many managed states have corresponding CSS pseudo-classes, such as :focus, and pseudo-elements, such as ::selection, that are also updated by the user agent.

##### Normative
Required for conformance. By contrast, content identified as informative or "non-normative" is not required for conformance.

##### Object
In the context of user interfaces, an item in the perceptual user experience, represented in markup languages by one or more elements, and rendered by user agents.

In the context of programming, the instantiation of one or more classes and interfaces which define the general characteristics of similar objects. An object in an accessibility API may represent one or more DOM objects. Accessibility APIs have defined interfaces that are distinct from DOM interfaces.
Ontology
A description of the characteristics of classes and how they relate to each other.

##### Owned Element
An 'owned element' is any DOM descendant of the element, any element specified as a child via aria-owns, or any DOM descendant of the owned child.

##### Perceivable
Presentable to users in ways they can sense. References in this document relate to WCAG 2 Principle 1; content must be perceivable [WCAG20].

##### Property
Attributes that are essential to the nature of a given object, or that represent a data value associated with the object. A change of a property may significantly impact the meaning or presentation of an object. Certain properties (for example, aria-multiline) are less likely to change than states, but note that the frequency of change difference is not a rule. A few properties, such as aria-activedescendant, aria-valuenow, and aria-valuetext are expected to change often. See clarification of states versus properties.

##### Relationship
A connection between two distinct things. Relationships may be of various types to indicate which object labels another, controls another, etc.

##### Role
Main indicator of type. This semantic association allows tools to present and support interaction with the object in a manner that is consistent with user expectations about other objects of that type.

##### Semantics
The meaning of something as understood by a human, defined in a way that computers can process a representation of an object, such as elements and attributes, and reliably represent the object in a way that various humans will achieve a mutually consistent understanding of the object.

##### State
A state is a dynamic property expressing characteristics of an object that may change in response to user action or automated processes. States do not affect the essential nature of the object, but represent data associated with the object or user interaction possibilities. See clarification of states versus properties.

##### Understandable
Presentable to users in ways they can construct an appropriate meaning. References in this document relate to WCAG 2 Principle 3; Information and the operation of user interface must be understandable [WCAG20].

##### User Agent
Any software that retrieves, renders and facilitates end user interaction with Web content. This definition may differ from that used in other documents.

##### Valid IDREF
A reference to a target element in the same document that has a matching ID

##### Value
A literal that solidifies the information expressed by a state, property, role, or text content.

##### acrWidget
Discrete user interface object with which the user can interact. Widgets range from simple objects that have one value or operation (e.g., check boxes and menu items), to complex objects that contain many managed sub-objects (e.g., trees and grids).

### ARIA Roles Model
The ARIA Roles Model defines the markup requirements for synchronizing front-end coding with the back-end behaviors documented in the User Agent Implementation Guide for browsers and Assistive Technologies.

### ARIA Supported States and Properties
The Supported States and Properties document specifies all available states and properties that are valid upon specific Roles.

[live demo](http://whatsock.com/tsg/Coding%20Arena/ARIA%20Toggles,%20Checkboxes,%20Links,%20and%20Buttons/ARIA%20Toggle%20Buttons/demo.htm)

## Aria Drag and Drop

##### There are 3 implementations of aria drag and drop.

* Unassociated: Where components are draggable with no associated drop zone.
* Associated: where drag and drop components require that the dragged component be dropped within the region of a drop zone.
* Internal: where drag and drop components consist of the draggable children of a parent control type.

## General Notes
Aria, or Accessible Rich Internet Applications, is is a set of attributes that define ways to make Web content and Web applications (especially those developed with Ajax, JavaScript and more recent web technologies like Bootstrap) more accessible to people with disabilities. For example, ARIA enables accessible navigation landmarks, JavaScript widgets, form hints and error messages, live content updates, and more.
[MDN Reference](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)

When ARIA is implemented correctly, you can literally change the nature of a custom web component in order to maximize accessibility for Assistive Technology users.

