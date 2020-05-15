---
page: markup
title: Markup
nav: Markup
order: 2
layout: default
updated: 14 May 2020
---

**This is a work in progress as we dump out thoughts and attempt to organize things.**

# Markup

As we work primarily with WordPress, you should follow the [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/) with the additions listed here.

We aim to meet the [WCAG accessibility guidelines](https://www.w3.org/TR/WCAG21/) at level AA.

## Accessibility

We believe strongly in an inclusive internet and aim to do our part. This starts with the markup. HTML is accessible and it falls on us to not break that.

### Standards

Although we aim to meet the [WCAG 2.1 Level AA](https://www.w3.org/TR/WCAG21/) guidelines, every Monkee-Boy project should pass at least Level A standards. Meeting Level AA helps a site comply with [Section 508](https://www.section508.gov/) in the US and the [EU Functional Accessibility Requirements](http://mandate376.standards.eu/standard/technical-requirements/#9).

A short summary of some of the main items we look for when approaching a project:

* Semantic and error free HTML.
* Ability to navigate by keyboard only, no traps.
* All content is available for all users.
* Content has a logical order.
* Dynamic changes on a page are announced.
* Minimum color contrast between text and background.
* Color alone doesn't convey meaning (like error messages).
* Animation can be stopped by the user.

### Testing

Automated testing can help us catch the baseline accessibility issues that can show up in our code. One way we can run automated tests is using [pa11y](https://github.com/pa11y/pa11y) via the command line. You can install it globally using `npm install -g pa11y@6.0.0-alpha pa11y-reporter-html`. Ideally running this should be part of your build process but you can use `pa11y --reporter html --ignore notice http://projectname.test > pa11y-report.html` to run a single report.

Manual testing is extremely important in catching accessibility issues. There are many tools to help walk you through manual testing, [Accessibility Insights](https://accessibilityinsights.io/) is a favorite. This process should be done by a developer using the [WCAG Quickref](https://www.w3.org/WAI/WCAG21/quickref/?versions=2.1&currentsidebar=%23col_overview&levels=aaa).

Do not rely only on automated testing as it won't catch everything and there could be false positives. Both tests should be conducted on a variety of pages/templates to generate the best result.

## Structure

Semantic markup gives meaning to the content you are wanting to present. This includes elements like `<header>`, `<nav>`, `<footer>`, and `<article>`. Readability is just as important for your code. This includes using the minium amount of markup you can, proper indentation, and consistent naming conventions.

### Schema.org

Schema.org markup allows you to provide content specific to search engines to improve how your search results are displayed. Schema markup shouldn't be used for the sake of including it, we should look for where it makes sense and the value it provides that project. Although there are a couple of ways to include this markup, it's recommended you use the JSON method.

Schema.org markup should be validated against the [Google Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool/).

### JavaScript

When using JavaScript to target specific HTML elements, prefix the ID or class with `js-`. This will indicate that the element has some related JS code and can help us avoid breaking that.

## Media

Creating accessible media falls on both the content creators and the development team. We should always be thinking about the best way to not only promote accessibility in content but making sure we are providing methods that are easy for content loaders to use.

### Images

Images can provide meaning to content, set the mood for a headline, or add a decorative flourish. Depending on the purpose of your image, determines the steps needed to make it accessible.

For images that provide meaning or is an important part of the content, you will want to provide appropriate alt text.

For images that are decorative or is redundant to the content, you will want to include an empty `alt=""` attribute.

Every image should have an alt attribute and having it empty is a valid use when the case calls for it.

When in doubt, reference the [W3C alt decision tree](https://www.w3.org/WAI/tutorials/images/decision-tree/).

### Audio & Video

When dealing with audio or video, it's important that audio descriptions, captions, and/or transcripts are provided. For us that means ensuring we have a system in place for that type of content to be loaded and displayed when needed.

We don't often deal with directly embedding audio or video but when needed, [Able Player](https://ableplayer.github.io/ableplayer/) provides a great start for an accessible media player.

## SVG

[optimizing, accessible, sprites]

## Fonts

[optimizing, limiting, display: swap]
