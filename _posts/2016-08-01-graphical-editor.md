---
layout: post
title:  "Refactoring Phoenix Contact's Graphical Editor: Embracing Testability & Extensibility"
summary: "During my tenure at Phoenix Contact, I restructured a graphical editor to enhance testability, introduced a comprehensive testing framework, and expanded functionalities. This journey underscored the value of adaptability in software development, revealing insights on the interplay between unit and integration tests."
author: twilker
date: '2016-08-01 14:35:23 +0530'
category: work
thumbnail: /assets/img/posts/logicplus/logic+.png
screenshots: 
video: https://www.youtube.com/embed/_bdMDCusUw0?si=4pI7ekUtAh1YoNpL
permalink: /work/graphical-editor/
language: CSharp
homepage: https://www.phoenixcontact.com/en-us/products/programming-plcnext-engineer-1046008
languages: C#
technologies: XAML, SpecFlow, MEF
timeinvestment: 4 years
ai-crafted: true
---

## Project Overview
At Phoenix Contact, I was entrusted with refining an existing graphical editor. My colleague had initiated the development, and an MVP was in place. My journey began by acquainting myself with the editor and recognizing potential avenues for improvement, especially in terms of testability.

## The Challenges
While the foundation of the editor was robust, its architecture didn't support testability. Object creation was intertwined with dependency management, making it a challenge to implement efficient unit tests.

## My Role & Approach
### Implementing Inversion of Control (IoC)
To address the testability challenge, my primary objective was to restructure the application by introducing IoC. This design pattern ensured that objects received their dependencies from outside rather than creating them internally, a change pivotal in enabling unit testing.

### Testing Framework Development
Post-restructuring, I developed a comprehensive testing framework. This involved both traditional unit tests and Behavior-Driven Development (BDD) style tests using SpecFlow. This layered testing approach ensured thorough coverage and efficacy.

## Additional Responsibilities
As I delved deeper into the project:

- **Feature Expansion**: I continually added new functionalities to the editor, like crafting routing algorithms.
- **SFC Editor Creation**: Drawing from the primary editor, I spearheaded the development of a new editor tailored for Sequential Function Chart (SFC). The central challenge here was devising an automatic arrangement algorithm.

## Outcomes & Legacy
The refactored editor base, enhanced for testability and extensibility, became a cornerstone within our framework. Various editors within the ecosystem have since been built upon this foundational architecture.

## Reflections & Lessons Learned
This project offered profound insights. Most notably, I discerned that unit tests might not always be the optimal choice, especially when the inner architecture is in flux. Integration tests, particularly with tools like SpecFlow, provide unparalleled reliability in such scenarios. Today, my testing strategy revolves around unit tests for high-permutation classes, like algorithms, while leaning on integration tests for broader functionalities.

## Future Directions
While I've transitioned from the project, further refinements have been made post my tenure. These enhancements focused on eliminating architectural inefficiencies and bolstering code readability.

## Conclusion
This project at Phoenix Contact was a testament to the importance of adaptability in software engineering. While established systems offer a foundation, continual introspection and restructuring pave the way for optimization, ensuring the software's longevity and efficacy.