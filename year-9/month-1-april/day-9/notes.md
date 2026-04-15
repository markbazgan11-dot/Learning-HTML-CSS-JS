# Year 9 — Day 9

## What I Did
Today was a massive pivot. I finally moved from pure HTML into the world of **CSS**, starting the Cafe Menu project on freeCodeCamp. It’s my first time actually making things look good instead of just plain text. I spent 
the session learning how to hook up stylesheets and getting the layout to actually sit right on the page.

--

## Improvements
1. **CSS Box Model:** Learned how to center containers using `margin-left: auto` and `margin-right: auto` with a `max-width` to keep things responsive so it doesn't look mid on mobile
2. **Visual Hierarchy:** Applied `background-image` to the body and used `burlywood` backgrounds for the menu to create that "cafe" aesthetic
3. **Typography & Links:** Mastered pseudo-classes like `:hover` and `:active` to make my links change color when you interact with them—major level up for UI
4. **Selector Grouping:** Learned how to use commas in CSS to style `h1`, `h2`, and `p` all at once, saving me from writing the same code over and over
5. **Image Alignment:** Figured out how to use `display: block` and auto margins to center images, since they don't behave like regular text elements
6. **Layout Flow:** Used `display: inline-block` to get the flavor names and prices to sit on the same line, making it actually look like a real menu

--

## Active Recall

**Q1: In CSS, what is the difference between `width: 500px` and `max-width: 500px`?**
A: If you just use `width`, it stays 500px even on a tiny phone screen, which breaks the layout and makes it scroll sideways. `max-width` lets the menu shrink on small screens but stops it from getting too huge on a desktop.

--

**Q2: What is the point of using a "fallback" font like `serif` after a specific font like `Impact`?** 
A: It’s basically a backup plan. If the user doesn't have `Impact` installed on their computer, the browser won't just break; it'll move to the next one in the list so the site still looks decent.

--

**Q3: What does the `:hover` selector do in your CSS menu?**
A: It's a pseudo-class that changes the style of an element (like my footer links) only when the mouse is sitting on top of it. I used it to turn the links brown so the user actually knows they are clickable.

--

**Q4: Why did we put the CSS link in the `<head>` instead of the `<body>`?**
A: You want the browser to load the "instructions" for how the page should look before it actually starts drawing the content. If you put it in the body, the page might flash unstyled text for a second before the CSS kicks 
in.

--

**Q5: What does `display: inline-block` actually do for your menu items?**
A: It's like the best of both worlds. It lets the elements sit next to each other on the same line (like text), but still lets you change their width and height (like a box). That’s how I got the price to sit right next 
to the coffee flavor.

--

## Reflection
Genuinely gassed about today. Seeing the Cafe Menu actually start to look like a real website instead of a basic HTML skeleton is a great feeling. It’s my first time touching CSS and it already feels way more creative than just writing tags. I’m starting to see how the dev side actually comes together to make something people would actually want to use.

--

## Tomorrow
- Keep pushing through the CSS Basics on freeCodeCamp—get deeper into the box model and colors
- Try to customize the cafe menu a bit more with some unique colors to see if I can break and fix the layout
- Start looking into how CSS Grid or Flexbox works since I've heard those are the "elite" ways to do layouts
