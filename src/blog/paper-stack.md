---
title: "| Paper stack |"
description: Paper stack its a creative-code art, created with Javascript.
author: Eduxdux
date: 2022-04-11T18:10:18.991Z
tags:
  - post
  - featured
image: /assets/blog/rnd14.png
imageAlt: Purple paper stack image
---
<!--StartFragment-->

![One of the final results of paper stack piece](/assets/blog/rnd14.png "One of the final results of paper stack piece")

## Paper Stack

Paper stack its a creative-code art, created with Javascript.*`(It will be launched on FxHash on April 16)`*

Initially my idea was to create only basic geometric shapes that by giving a false extrude create a certain 3d appearance.

![initital idea of paper stack](https://www.notion.so/image/https%3A%2F%2Fs3.us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F76abbf2d-313d-4178-9f33-553ec023a916%2Fowip1.jpg%3FX-Amz-Algorithm%3DAWS4-HMAC-SHA256%26X-Amz-Content-Sha256%3DUNSIGNED-PAYLOAD%26X-Amz-Credential%3DAKIAT73L2G45EIPT3X45%252F20220325%252Fus-west-2%252Fs3%252Faws4_request%26X-Amz-Date%3D20220325T182049Z%26X-Amz-Expires%3D86400%26X-Amz-Signature%3D0e398baa628508362a71fbd32775f4adf1d554636c6c0c37a90d15bd7ec4f838%26X-Amz-SignedHeaders%3Dhost%26x-id%3DGetObject?table=block&id=0055a448-dad5-4784-99dc-c5da7ac47920&cache=v2)

The initial visualization was simpler, with fewer grid elements and flatter colors, with less detail. But I still didn't like it enough.

Taking advantage of the situation of a new sketch, I wanted to make a grid that the size of the cells were proportional to the size of the canvas, I had already done this before using a nested loop, however, watching [Bruno Imbrizi's course on Canvas-Sketch](https://www.domestika.org/pt/courses/2729-programacao-criativa-produza-pecas-visuais-com-javascript) he uses a technique to form the grid using only one loop, as I found it interesting I decided to implement it in this project.

```javascript
for (let i = 0; i < numCells; i++){
    let col = i % cols;
    let row = floor(i / cols);
}
```

The code worked like a glove, I had to make only minor adjustments, trying to keep in mind that when you extrude the visual weight and the elements move just beyond the center axis of each cell. And so I decided to expand the visualization to take up the entire space of the canvas, rather than just a centered element.

After that the biggest job was to stylize the piece so that the volume could appear at the same time to be something visually interesting without appearing to have been done with Blender.

After styling I decided that cell height x brightness randomization gets too chaotic when used only from the random() function, and the solution would be to use a noise() that would create a "lighter" and more visually pleasing randomization.

![This was one of the WIPs I sent to Aag, at that point I had started styling, for the texture I used a pattern library in p5.js (I'll talk about the libraries below)](https://www.notion.so/image/https%3A%2F%2Fs3.us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F46ef78de-7bf4-4b8a-93bf-1d13eaf626e7%2Fphoto_2022-03-07_20-06-32.jpg%3FX-Amz-Algorithm%3DAWS4-HMAC-SHA256%26X-Amz-Content-Sha256%3DUNSIGNED-PAYLOAD%26X-Amz-Credential%3DAKIAT73L2G45EIPT3X45%252F20220325%252Fus-west-2%252Fs3%252Faws4_request%26X-Amz-Date%3D20220325T182049Z%26X-Amz-Expires%3D86400%26X-Amz-Signature%3D664df22b1a01fcaefcbef3faa617f8f814758ecd5124a1ba811aec17ffec0a84%26X-Amz-SignedHeaders%3Dhost%26x-id%3DGetObject?table=block&id=3d21c162-a8b9-4951-aa8d-fa78025b50bc&cache=v2 "This was one of the WIPs I sent to Aag, at that point I had started styling, for the texture I used a pattern library in p5.js (I'll talk about the libraries below)")

This was one of the WIPs I sent to Aag, at that point I had started styling, for the texture I used a pattern library in p5.js (I'll talk about the libraries below)

#### [](https://eduxdux.xyz/paper-stack#8729491d241642bb985c4704db8f99ba "Libs")

After getting a good shape from these stacked papers, I started thinking about how to get a depth. To achieve this, I needed a way to control the brightness concatenated with the "height" of the paper, after a few hours of searching I found chroma.js, and god this saved me a lot of time, if I hadn't found it I would first need to convert my palette from HEX to HSB and then get the brightness value.

With chroma.js I just added a few lines and got what I wanted

#### Libs

Since I don't have the greatest patience in the world I look for small (or large) solutions to help me stylize and facilitate my work. And here it was no different, I used libraries for p5.js and for Js in general.

For this project I’ve used:

p5 Scribbles

<https://github.com/generative-light/p5.scribble.js>

p5 patterns

<https://github.com/SYM380/p5.pattern>

chroma.js

<https://github.com/gka/chroma.js>

<!--EndFragment-->