---
title: Blog
summary: Technical notes on my research
type: landing

cascade:
  - _target:
      kind: page
    params:
      show_breadcrumb: true

sections:
  - block: collection
    id: posts
    content:
      title: Posts
      filters:
        folders:
          - post
    design:
      view: article-grid
      columns: 2
---
