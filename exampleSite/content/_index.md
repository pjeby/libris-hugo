---
title: Home
blocks:
  - id: hero
    type: hero
    title: Hero Section
    image: images/5.jpg
    content: |-
      This section can contain a subtitle or tagline. The recommended length is one to three sentences, but can be changed as you prefer.
    actions:
      - label: Get Started
        url: "/docs"
  - id: cards
    type: cards
    highlight: true
    stretch: true
    cards:
      - title: Documentation
        content: |-
          Donec lobortis velit sed suscipit lobortis. Ut non quam metus. Nullam a maximus mi. Quisque justo nunc, sollicitudin euismod euismod at, tincidunt ut tellus. Vivamus rhoncus mattis varius.
        actions:
          - label: Get Started
            url: "/docs"
      - title: Blog
        content: |-
          Vestibulum a nunc ut eros condimentum posuere. Nullam dapibus quis nunc non interdum. Pellentesque tortor ligula, gravida ac commodo eu.
        actions:
          - label: View Posts
            url: "/blog"
      - title: Style Guides
        content: |-
          Donec lobortis velit sed suscipit lobortis. Ut non quam metus. Nullam a maximus mi. Quisque justo nunc, sollicitudin euismod euismod at, tincidunt ut tellus. Vivamus rhoncus mattis varius.
        actions:
          - label: Learn More
            url: "/style-guide.html"
  - id: text-img
    type: content
    image: images/10.jpg
    title: A Section With An Image
    content: |-
      Nam pulvinar ante eu ultricies volutpat. Sed nulla nibh, dapibus sit amet cursus quis, fringilla nec sapien. Vestibulum imperdiet nunc bibendum consectetur lobortis.
    actions:
      - label: View Demo
        url: "/docs/getting-started"
      - label: Get Started
        url: "/docs/getting-started"
  - id: cards-two-col
    type: cards
    stretch: true
    highlight: true
    title: Sample Layouts
    subtitle: >-
      An optional subtitle of the section
    cards:
      - title: Overview
        content: |-
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec nisl ligula, cursus id molestie vel, maximus aliquet risus. Vivamus in nibh fringilla, fringilla tortor at, pulvinar orci.
        actions:
          - label: Learn More
            url: "/docs/overview.html"
      - title: Showcase
        content: |-
          Donec lobortis velit sed suscipit lobortis. Ut non quam metus. Nullam a maximus mi. Quisque justo nunc, sollicitudin euismod euismod at, tincidunt ut tellus. Vivamus rhoncus mattis varius.
        actions:
          - label: Learn More
            url: "/showcase.html"
  - id: cta
    type: cta
    title: The Title of The Call to Action Block
    subtitle: >-
      This is an optional description for the call to action block.
    actions:
      - label: Get Started
        url: "/docs/getting-started/installation"
  - id: text-no-img
    type: content
    title: A Section Without Image
    content: |-
      Nam pulvinar ante eu ultricies volutpat. Sed nulla nibh, dapibus sit amet cursus quis, fringilla nec sapien. Vestibulum imperdiet nunc bibendum consectetur lobortis.
    actions:
      - label: Get Started
        url: "/docs/getting-started/installation"
menus:
  main:
    weight: 1
    title: Home
layout: home
---
