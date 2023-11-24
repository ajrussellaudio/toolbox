# The Alan Russell Toolbox

A highly opinionated guide to the libraries, tools and other stuff used by God's gift to JavaScript, Alan Russell.

## Philosophy

- [Red, Green, Refactor](https://www.codecademy.com/article/tdd-red-green-refactor)
- [Laziness, Impatience, Hubris](https://wiki.c2.com/?LazinessImpatienceHubris)
- [Web design is 95% typography](https://ia.net/topics/the-web-is-all-about-typography-period)

## Front end

### [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)

Write tests! Tests help us sleep at night. Tests give us confidence that our code works while we're writing it, and confidence that we aren't breaking old code while we write new code elsewhere. Tests tell the next dev to read our code how we expected it to work, and makes them hate us a little less.

React Testing Library encourages us to test our React app in the same way that a user would use it. We don't care about the implementation of our components, only the behaviour; we only care that a given set of inputs or user actions lead to a desired outcome. Which is good.

### [Vite](https://vitejs.dev/)

Create React App died. We are all very sad about it. Vite is now the "standard" way to get started quickly with a React app... or a Vue app, or a Svelte app, or thanks to its [awesome community support](https://github.com/vitejs/awesome-vite) a frontend JS/TS app in almost any library you can think of.

### [React Query](https://tanstack.com/query/v3/docs/react/overview)

`fetch` inside a `useEffect` hook is _rubbish_. React Query takes the pain out of fetching data from a server API and making it available to your components. It also handles a load of common "gotchas" for free, like caching requests (so that if our component re-requests data from the same endpoint no new request is fired for a given time limit) and de-duplicating requests (so that if two components fetch the same data simultaneously, only one request is fired).

See also: [SWR](https://swr.vercel.app/) - same ideas, built by Vercel, but the docs aren't as good.

### [React Hook Form](https://react-hook-form.com/)

Building a `<form>` in React is _rubbish_. The old React docs [basically admit this](https://legacy.reactjs.org/docs/forms.html), the new docs [promise extensions to the `<form>` component](https://react.dev/reference/react-dom/components/form) which might be awesome, or which might suck even harder. In the meantime, React Hook Form abstracts away most of the grunt work involved in form submission, validation and error handling, and using it doesn't feel like punching yourself in the face.

See also: [Formik](https://formik.org/) which is arguably more popular, but the code looks ugly to me, especially in TypeScript, and this is my list!

### [Storybook](https://storybook.js.org/)

Build your components in isolation. As a developer, Storybook lets you experiment with your CSS without the headache of having to load your components into an app. A Storybook can also be the closest thing to documentation you'll find in a front end codebase, as seen in the wild with [BBC iPlayer](https://www.bbc.co.uk/iplayer/storybook/index.html?path=/story/playground--blank), [GOV.UK](https://govuk-react.github.io/govuk-react/?path=/docs/welcome--docs) and [Skyscanner](https://backpack.github.io/storybook/index.html?path=/docs/bpk-animate-height--documentation)

I actually prefer [Ladle](https://ladle.dev/) as it's more lightweight and snappy, but it's new and their docs don't feel done yet.

### [MSW](https://mswjs.io/) (Mock Service Worker)

Usually the front end team have to build the UI while the back end team work on the API. This means the UI has no API to query yet! MSW mocks the response to server requests, so your app works even when the API isn't done yet. It works in the browser and in tests, total baller.

### [React Icons](https://react-icons.github.io/react-icons/)

Inevitably we will want an X button to close a pop-up, or a cogwheel icon on the Settings menu link, or a Facebook logo on the social links, or a croissant icon for some reason. You could go through the faff of signing up for [Font Awesome](https://fontawesome.com/start), or finding royalty-free vector images somewhere online, or you could install React Icons, import the icon you need and go about your day. Up to you.

## Backend

### [Sanity](https://www.sanity.io/)

At CodeClan we focussed pretty solidly on data-driven applications - grabbing data from a server and displaying it on the client, or sending data from the client to the server and persisting it. The alternative to a data-driven app is a content-driven app, where content (text, images, video...) is created by non-technical people and displayed for the web by our frontend apps.

Sanity is a headless content management service (CMS), meaning it does all the backend work of storing content and making it available to our apps, but has no opinion on how our client-side apps should be written. It gives us an editor UI, so non-technical content editors (e.g. marketing people, copywriters) can edit content without ever bothering us developers. It also gives us neat ways of fetching our content from React, Next, React Native and heaps of other frameworks.

### [NestJS](https://nestjs.com/)

A highly scalable Node.js backend that encourages good practices like modular code and dependency injection (the D in SOLID). Nest makes most of the high-level architectural decisions for us, and comes with a load of command line generators that even write the code for us! Using Nest we developers end up writing only short snippets of "glue" code to connect Nest to our data source and we're done.

### [Prisma](https://www.prisma.io/)

Makes data persistence so easy it feels like cheating. You define the schema (the shape of the data), tell Prisma to "generate" and it handles the rest. It builds a database in PostgreSQL, Mongo or others, writes the migrations that allow us to build an identical database somewhere else (e.g. AWS), and it even generates TypeScript types for our data, letting us lean heavily on our editor's autocomplete when querying and mutating our data in our code.

## Online tools

### [Can I Use...](https://caniuse.com/)

For when you need to check if that cool new web standard works in Safari yet.

### [SpinKit](https://tobiasahlin.com/spinkit/)

Loading spinners in pure CSS.

### [UI Gradients](https://uigradients.com/)

Gradients seem to be in fashion again. But really who has time to actually write one out?

### [Type Scale Generator](https://baseline.is/tools/type-scale-generator/)

[Web design is 95% typography](https://ia.net/topics/the-web-is-all-about-typography-period). This site goes beyond Google Fonts and generates code for CSS, Sass and Tailwind to make sure all your font sizes look dope together.

### [RegExr](https://regexr.com/)

Working with RegEx gives me heartburn, but sometimes it's unavoidable. RegExr gives you a RegEx playground where you can enter some test strings and experiment with regular expressions until you get the matches you want, then copy/paste that cursed nonsense into your code.

Wait, what is RegEx? [Good luck](https://coderpad.io/blog/development/the-complete-guide-to-regular-expressions-regex/).

### [explainshell](https://explainshell.com/)

Takes a shell command like `rm -rf node_modules` and... explains it! Breaks down the command (`rm`) and the flags (`r` and `f`) and tells you what they all do. Very useful when you find a "magic" command on Stack Overflow or from a colleague and want to understand what it actually does.

### [Learn X in Y Minutes](https://learnxinyminutes.com/)

Cheat sheets for any programming language you can think of. Since we know how Python, JavaScript and Java all work, we can solve problems in really any language. But we might not know the _syntax_ for a function in Rust or a for loop in PHP or printing to the screen in C++. The building blocks are all the same in every language, only the syntax changes. That's where this site comes in.

## Other JavaScript stuff

### [Jest](https://jestjs.io/)

This should be higher, but it's a biggie for both front end and back end JavaScript projects. Testing is crucial and Jest has the best developer experience of the many JS testing libraries.

### [D3](https://d3js.org/)

For building seriously cool interactive graphs and data visualisation. It's such a cool library but it's never been good friends with React. For cool graphs in React try Airbnb's [Visx](https://airbnb.io/visx/), but their docs suck and you'll need to know how D3 works first anyway.

### [P5.js](https://p5js.org/)

[Processing](https://processing.org/) for the web, creative coding with really neat abstractions around a lot of actually pretty complex maths, geometry and graphics stuff. The docs are excellent, but also check out [Coding Train](https://thecodingtrain.com/) for some really fun tutorials and codealong videos aimed at beginners.

### [Three.js](https://airbnb.io/visx/)

3D modelling on the web. Better performance than P5 in 3D mode, but not as fun to work with.

### [Tone.js](https://tonejs.github.io/)

Useful abstractions around the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) especially for synth nerds like me.

## Not JavaScript

### [Processing](https://processing.org/)

Hell yeah.

### [SuperCollider](https://supercollider.github.io/)

This was my "gateway drug". Before I started CodeClan I played around with this. I made some music that didn't suck with nothing but code and thought cool, I wonder what else code can do. Now I'm a web developer.

SuperCollider is a platform for audio synthesis (making sound) and algorithmic composition (letting the computer decide what notes to play and when, based on your rules). It's both an incredibly powerful synthesizer and a language to program it with. The language shares a common ancestor with Java and JavaScript so there's `{}` curly brackets everywhere, but really it's its own thing. Big learning curve but it's mad fun. People have literally made whole albums in SuperCollider.

### [Sonic Pi](https://sonic-pi.net/)

If you want to make music with code but SuperCollider is too nerdy for you, there's Sonic Pi. It's designed for kids and is lightweight enough to run on an older Raspberry Pi. Behind the scenes it's a Ruby wrapper around SuperCollider, but it doesn't look much like regular Ruby either. It's really popular in the live coding music scene, known as "algorave".

## The Future

My current list (Nov 23) of things that look interesting, but I haven't had time to check out yet. If anything here is cool, let me know.

- [Remix](https://remix.run/) - framework for React, alternative to NextJS.
- [Astro](https://astro.build/) - framework for content-driven sites
- [Rust](https://www.rust-lang.org/) - low-level systems language, similar in purpose to C/C++ but with better syntax and developer experience.
- [WASM/WebAssembly](https://webassembly.org/) - for building stupidly high-performance web apps. Actually a compilation target for languages like TypeScript and Rust, not something you'd write yourself.
- [A Cloud Guru](https://www.pluralsight.com/cloud-guru) - a learning platform for AWS, Azure and friends with both casual courses and professional certifications.
