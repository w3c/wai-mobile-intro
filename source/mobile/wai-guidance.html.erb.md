---
title: WAI Guidance and Techniques for Mobile Accessibility
nav_title: WAI Guidance
order: 2
status: editors-draft
editors:
  - Kim Patch
  - Kathy Wahlbin
  - Judy Brewer
contributors:
  - The Education and Outreach Working Group (<a href="https://www.w3.org/WAI/EO/">EOWG</a>)
support: Developed with support from the <a href="https://www.w3.org/WAI/WCAGTA/">U.S. Access Board, WCAG TA Project</a>
---

## WCAG 2.0

Many [WCAG 2.0](https://www.w3.org/TR/WCAG20/) techniques apply to web and non-web mobile content and applications.

_[[[Note from Kim: I wanted to put the customizable quick reference here with advice to click the mobile tag, but there is no mobile tag. This might be good to keep in mind for future version of the customizable quick reference.]]]_

[Mobile Accessibility: How WCAG 2.0 and Other W3C/WAI Guidelines Apply to Mobile](https://www.w3.org/TR/mobile-accessibility-mapping/) maps out in detail how many of the W3C/WAI Guidelines apply to mobile.

## UAAG 2.0 Guidelines

The [UAAG 2.0](https://www.w3.org/TR/2015/NOTE-UAAG20-Reference-20151215/) guidelines apply to mobile.

Many of the guidelines include [mobile examples](https://www.w3.org/TR/IMPLEMENTING-UAAG20/mobile.html)

##W3C Tutorials

The W3C [Tutorials](https://www.w3.org/WAI/tutorials/) for Page Structure, Menus, Images, Tables, Forms and Carousels menus all apply to mobile.

## Issues to bear in mind when using general accessibility resources for mobile

Mobile devices are used differently because they have small screens, are very portable, and the primary means of input is often touch.

### 1. Limited screen size
Although mobile devices have exceptional resolution, small screen sizes limit how much information can be viewed at once, especially for people who use magnification.

Tips:

- Provide clear information architecture and navigation
- Minimize distractions
- Provide perceptible feedback
- Use responsive design that uses CSS stylesheets to adjust layout depending on screen width
- Make sure text reflows to avoid horizontal scrolling
- Provide a reasonable default size for content and touch controls
- Adapt the length of link text to screen width
- In portrait layout, position form fields below rather than beside labels

Details:

- [Small screen size](https://www.w3.org/TR/mobile-accessibility-mapping/#small-screen-size)

### 2. Touch and gestural input

The exceptional resolution of mobile screen devices means that interactive elements can be shown in a small space. But these elements must be accessible by touch.

Tips:

- Make touch targets large enough to be accessible by touch (without magnification)
- Make touch targets look clickable/touchable
- Use inactive space to separate touch targets that are close together
- Position and group touch targets so they are easy to reach on a mobile device
- Focus target on touch, activate target on release (mouseup or touchend)
- Make gestures easy to carry out

Details:

- [Touch target size and spacing](https://www.w3.org/TR/mobile-accessibility-mapping/#touch-target-size-and-spacing)
- [Touchscreen gestures](https://www.w3.org/TR/mobile-accessibility-mapping/#touchscreen-gestures)
- [Placing Buttons where they are easy to access](https://www.w3.org/TR/mobile-accessibility-mapping/#placing-buttons-where-they-are-easy-to-access)
- [Provide clear indication that elements are actionable](https://www.w3.org/TR/mobile-accessibility-mapping/#provide-clear-indication-that-elements-are-actionable)


### 3. Keyboards and virtual keyboards

Although the primary means of input for mobile devices is touch, mobile devices also include on-screen keyboards and can connect to external input devices including  keyboards. Some users rely on keyboard input.

Tips:

- Support keyboard input as an alternative to touch

Details:

- [Keyboard control for touchscreen devices](https://www.w3.org/TR/mobile-accessibility-mapping/#keyboard-control-for-touchscreen-devices)

### 4. Speech

Mobile devices commonly support speech input via a speech button on the keyboard and intelligent agents like Siri. Some users rely on speech input.

Tips:

- Support speech input as an alternative to touch
- If you offer keyboard users single character shortcuts, make sure users can turn off or remap these shortcuts so they can avoid accidentally activating many shortcuts at once with spoken words

### 5. Device sensors

Mobile devices commonly support control options triggered by device manipulation gestures.  Some users cannot carry out these gestures.

Tips:

- Provide touch and keyboard operable alternative control options for device manipulation gestures

Details:

- [Device manipulation gestures](https://www.w3.org/TR/mobile-accessibility-mapping/#device-manipulation-gestures)


### 6. Layout and screen orientation

Most sites today use responsive design to adjust layout based on screen size. People using mobile devices must scroll more. People with low vision who use magnification may be seeing the mobile version on the desktop. Some users may not able to easily change orientation.

Tips:

- Don’t assume that a given screen width is only for a particular device. Make sure all functions are available four screens of all sizes, and make sure that layout is relatively consistent in all sizes and for both portrait and landscape mode.
- Position important elements in the first part of the page to limit excessive scrolling
- Warn users when moving between portrait and landscape mode

Details:

- [consistent-layout](https://www.w3.org/TR/mobile-accessibility-mapping/#consistent-layout)
- [Positioning important page elements before the page scroll](https://www.w3.org/TR/mobile-accessibility-mapping/#positioning-important-page-elements-before-the-page-scroll)
- [Changing screen orientation portrait landscape](https://www.w3.org/TR/mobile-accessibility-mapping/#changing-screen-orientation-portrait-landscape)

### 7. Platform accessibility conventions

Mobile devices include accessibility features like zoom, large fonts, and captions. It’s important that a website not interfere with the operation of this platform-wide assistive technology

Tips:

- Honor platform accessibility settings including zoom, fonts and captions

Details

- [Support the characteristic properties of the platform](https://www.w3.org/TR/mobile-accessibility-mapping/#support-the-characteristic-properties-of-the-platform)

