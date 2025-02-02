---
id: intro
title: Angular Testing Library
sidebar_label: Introduction
---

[`Angular Testing Library`](https://github.com/testing-library/angular-testing-library)
builds on top of
[`DOM Testing Library`](https://github.com/testing-library/dom-testing-library)
by adding APIs for working with React components.

```bash
npm install --save-dev @testing-library/angular
```

- [`@testing-library/angular-testing-library` on GitHub](https://github.com/testing-library/angular-testing-library)

## The problem

You want to write maintainable tests for your Angular components. As a part of
this goal, you want your tests to avoid including implementation details of your
components and rather focus on making your tests give you the confidence for
which they are intended. As part of this, you want your testbase to be
maintainable in the long run so refactors of your components (changes to
implementation but not functionality) don't break your tests and slow you and
your team down.

## This solution

The `Angular Testing Library` is a very lightweight solution for testing Angular
components. It provides light utility functions on top of
[`DOM Testing Library`](https://github.com/testing-library/dom-testing-library)
in a way that encourages better testing practices. Its primary guiding principle
is:

> [The more your tests resemble the way your software is used, the more confidence they can give you.](guiding-principles.md)

So rather than dealing with instances of rendered Angular components, your tests
will work with actual DOM nodes. The utilities this library provides facilitate
querying the DOM in the same way the user would. Finding for elements by their
label text (just like a user would), finding links and buttons from their text
(like a user would). It also exposes a recommended way to find elements by a
`data-testid` as an "escape hatch" for elements where the text content and label
do not make sense or is not practical.

This library encourages your applications to be more accessible and allows you
to get your tests closer to using your components the way a user will, which
allows your tests to give you more confidence that your application will work
when a real user uses it.

The `Angular Testing Library`:

- Re-exports the `query` and `fireEvent` utility functions from
  [`DOM Testing Library`](https://github.com/testing-library/dom-testing-library).
- Encapsulates the `fireEvent` functions of your component to automatically call
  `detectChanges()` after an event occurs
- Is test framework agnostic, it runs on every test framework
