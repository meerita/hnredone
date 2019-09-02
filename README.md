# Hacker News Redone

This project was made to demonstrate the power of the functional CSS and proper HTML techniques on Hacker News frontpage.

Everything started with this post: https://news.ycombinator.com/item?id=20854214 that talks about how good is that HN wasn't redesigned due the OP was browsing it with slow connection. I though I could make HN even faster without changing the essence of the design too much. So I decided to re-do Hacker News using the [Utilitarian CSS Framework](https://github.com/meerita/utilcss) to output the minimum CSS and test both performance gains in HN on a local server.

## What we want to test

Here are the things tested:

1. Loading speed of resources
2. Rendering average
3. Painting Average
4. Comparison of sizes
5. Total build time

### Results

Average results for 15 tries, same webserver, machine

|   | Original | Hacked |
|:-:|:-:|:-:|
| Load | 50,77ms | 17,9ms |
| Render | 59,3ms  | 22ms |
| Painting | 14ms | 6ms |
| Requests | 7 | 2 |
| Finish | 270,2ms| 83,7ms |

This by no means is perfect, but the idea is to demonstrate that even no CSS can be slower (the browser uses its own CSS and it's slow by default too).

## Approach

First, we will have both projects in different folders and we load them into a webserver, and do several performance tests to get the averages.

The hacked version will contain these main changes:

1. 0 images used. No blinking effect. We will rely on base64 or embebed SVG when possible.
2. No external stylesheet. We will print the CSS on the head of the document.
3. The HTML will be redone using different techniques
4. We will rely on CSS-grid, Flex and other things. HN audience is l33t.
5. Must look nice on Lynx.

## Notes

The usage of images in HN makes the page load and render slower in average. You can see this effect: first paints the entire page, then repaint happens with all the small arrows. The embebed one doesn't have repaints. It's way faster.

Since the stylesheet is less than 1545 bytes, I added it to the HEAD of the document. This increases the loading, rendering time by a lot due the high priority of the queue with tcp connections. The trade off is minimal and you can build the entire HN with that CSS instructions.

CSS grid made the HTML reduced and more readeable, for example, we don't rely anymore on tables under tables. Also, with the CSS at the HEAD, we will always be able to render the page properly. All HN audience has modern updated browsers.

You can really enjoy HN on Lynx. The [current version is not good on lynx](https://i.imgur.com/giUTzH0.jpg) but [the hacked one looks amazing](https://i.imgur.com/1MTT4wz.jpg).
