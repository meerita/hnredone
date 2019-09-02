# Hacker News Redone

This project was made to demonstrate the power of the functional CSS and proper HTML techniques on Hacker News frontpage.

Everything started with this post: https://news.ycombinator.com/item?id=20854214 so I decided to re-do Hacker News using the [Utilitarian CSS Framework](https://github.com/meerita/utilcss) to output the minimum CSS and test both performance gains in HN on a local server.

## What we want to test

Here are the things tested:

1. Loading speed of resources
2. Rendering average
3. Painting Average
4. Comparison of sizes
5. Total build time

This by no means is perfect, but the idea is to demonstrate that even no CSS can be slower (the browser uses its own CSS and it's slow by default too).

## Approach

First, we will have both projects in different folders and we 

The UCSS one will contain these main changes:

1. 0 images used. We will rely on base64 or embebed SVG when possible.
2. No external stylesheet. We will print the CSS on the head of the document.
3. The HTML will be redone using different techniques
4. We will rely on CSS-grid, Flex and other things. HN audience is l33t.
5. Must look nice on Lynx.
