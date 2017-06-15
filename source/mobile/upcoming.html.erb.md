---
title: Upcoming
order: 7
status: editors-draft
wcag_success_criteria:
wcag_techniques:
editors:
  - Kim Patch
  - Kathy Wahlbin
  - Judy Brewer
contributors:
  - The Education and Outreach Working Group (<a href="https://www.w3.org/WAI/EO/">EOWG</a>)
support: Developed with support from the <a href="https://www.w3.org/WAI/WCAGTA/">U.S. Access Board, WCAG TA Project</a>
---
##Areas of work under development
The WCAG mobile task force is working to point out ways to ensure accessibility on mobile devices.

Here are some of the issues the task force has identified, proposed success criteria for, and generated discussion about. Note that these are all still under discussion and may or may not become part of a standard.

These can be useful as non-normative success criteria for interim consideration by developers.

###Character Key Shortcuts

* **Issue:** Character key shortcuts are useful for keyboard users, but detrimental for speech input users.
* **Proposed solution:** Allow input users to turn off or change character key shortcuts.
* **Discussion:** [Character Key Shortcuts](https://github.com/w3c/wcag21/issues/69)
* Character Key Shortcuts is proposed for [WCAG 2.1](PLACEHOLDER) (PLACEHOLDER)

###Concurrent Input Mechanisms
* **Issue:** Users sometimes use multiple input mechanisms.
* **Proposed solution:** Ensure that all functionality works even when a user switches between input mechanisms.
* **Discussion:** [Concurrent Input Mechanisms](https://github.com/w3c/wcag21/issues/64)

###Device Sensors
* **Issue:** Some users can’t physically move a mobile device.
* **Proposed solution:** Allow users to operate functionality without requiring device sensor information unless the device sensor is essential for a function and not using it would invalidate the activity.
* **Discussion:** [Device Sensors](https://github.com/w3c/wcag21/issues/67)

###Keyboard with Assistive Technology
* **Issue:** Some assistive technologies remap keyboard shortcuts.
* **Proposed solution:** Ensure that functions are still available by keyboard when assistive technology is on.
* **Discussion:** [Keyboard with Assistive Technology](https://github.com/w3c/wcag21/issues/62)

###No accidental activation
* **Issue:** It can be easy to accidentally touch elements on a touchscreen.
* **Proposed solution:** Activate on the up-event and make activation reversible.
* **Discussion** of [No Accidental Activation](https://github.com/w3c/wcag21/issues/65)
* No accidental activation is proposed for [WCAG 2.1](https://rawgit.com/w3c/wcag21/orientation_ISSUE-70/guidelines/#accidental-activation)

###Non-interference with Assistive Technology
* **Issue:** There can be conflicts between standard mobile technologies and assistive technology that users might have for mobile devices.
* **Proposed solution:** Ensure that content doesn’t interfere with the normal operation of the platform assistive technology.
* **Discussion:** [Non-interference with Assistive Technology](https://github.com/w3c/wcag21/issues/71)

###Orientation
* **Issue:** Some users can’t change screen orientation on a mobile device.
* **Proposed solution:** Allow users to choose between portrait and landscape orientation unless the orientation is essential for the use of the content.
* **Discussion:** [Orientation](https://github.com/w3c/wcag21/issues/70)

###Pointer
* **Issue:** Some users require pointer input.
* **Proposed solution:** Ensure that users can operate all functionality using pointer input.
* **Discussion:** [Pointer](https://github.com/w3c/wcag21/issues/59)

###Pointer Gestures
* **Issue:** Some users can’t use pointer gestures like pinch and zoom.
* **Proposed solution:** Provide a way for users to operate pointer gestures using simple pointer input.
* **Discussion:** [Pointer Gestures](https://github.com/w3c/wcag21/issues/61)

###Pointer Inputs with Additional Sensors
* **Issue:** Some users can’t use controls that require more than position, e.g. pressure, tilt information.
* **Proposed solution:** Provide a way to operate functionality that doesn’t require information like pressure and tilt.
* **Discussion:** [Pointer Inputs with Additional Sensors](https://github.com/w3c/wcag21/issues/66)

###Speech Input
* **Issue:** Hidden commands are detrimental for speech input users.
* **Proposed solution:** Provide discoverable, accessible names for screen elements.
* **Discussion:** [Speech Input](https://github.com/w3c/wcag21/issues/68)

###Target Size
* **Issue:** Some users have trouble using a pointer with small targets.
* **Proposed solution:** Ensure that all users can access touch targets.
* **Discussion:** [Target Size](https://github.com/w3c/wcag21/issues/60)

###Touch with Assistive Technology
* **Issue:** Some assistive technologies remap touch gestures.
* **Proposed solution:** Ensure that functions are still available by touch when assistive technology is on.
* **Discussion:** [Touch with Assistive Technology](https://github.com/w3c/wcag21/issues/63)


##What to watch for
Here are some key areas watch as mobile devices continue to develop.

- Better support for smaller screen sizes, including different screen resolutions and sizes and the expectation that screens can be oriented vertically or horizontally

- Better support for multiple input methods, and for using multiple input methods simultaneously. These may include
    - Touch
    - Gesture
    - Stylus
    - Mouse
    - Keyboard
    - Device sensors including actuator, compass
    - Touch with multiple pressure points
    - Stylus with multiple pressure points and angle variables

Desktop users have long been combining keyboard and mouse on the desktop. Speech input desktop users often combine speech and mouse. Mobile users are increasingly combining touch and speech.

- Better support for specific assistive technology and device accessibility settings
