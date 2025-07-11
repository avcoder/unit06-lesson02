---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /assets/intro.jpg
# some information about your slides (markdown enabled)
title: Software Development | Foundations
info: |
  ## Software Development | Foundations
# apply unocss classes to the current slide
class: text-left
drawings:
  persist: false
transition: slide-left
mdc: true
---

# React: JSX
Frontend Development: Unit 06 - Lesson 02

- [ ] JSX
- [ ] Covering 'gotchas'
- [ ] Conditionals

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
-->

---
transition: slide-left
---

# Recap

- reminder: Algorithm and Data Structure Assignment due Jul. 20 
- repo of where we left off: https://github.com/avcoder/test-react
- [last time](https://unit06-lesson01.netlify.app/1) we just finished replacing the App.tsx `<button>` with our `<Button>` component

---
transition: slide-left
---

# Common Gotchas
Try the following common errors to see what errors look like in React.  Find solutions for each.

- Forgetting to `return` JSX
- Confusing camelCase for HTML attributes `onclick vs onClick`
- Using `class` instead of `className`
- if using inline styles, using hyphenated names instead of camelCase 
  - ex: `background-color vs backgroundColor`
- Multiple top-level elements without a wrapper/fragment
- DON'T use if statements directly inside JSX like `return ( if (isLoggedIn) { <p>Welcome</p> });`
- Not using `key` in lists
- JSX requires properly closed tags, even for void elements. ex: `<input /> <br />`
- what happens if props are undefined? ex: `return (<div className={someUndefinedClass}>Hi</div>)`
- if `numOfItems` is 0, this will render 0 `{numOfItems && <ShoppingList items={shoppingList} />}`
- examine if there are any more red squiggly lines in VSCode? 

---
transition: slide-left
---

# Exercise: Use React DevTools to find component
- Install React DevTools for your browser and explore it (should be similar to Vue DevTools)
- Goto: instagram.com
   - Try to find the React component for the Login button
   - why do the React components look weird/minified? (prod vs development)
   - Try to change a value of a prop in any component to see what might happen
- View your local App.tsx again in the browser
  - Just like you right-click inspect DOM element to find that particular HTML element in the DOM, you can do similar with React components
  - try changing prop values (like `label`)
  - Tip: in Chrome devtools, can use `Cmd + p` to find React filename

---
transition: slide-left
---

# Separation of Concerns

<img src="/assets/sepconcerns.png" style="height: 450px">

---
transition: slide-left
---

# Exercise: Draw components
Use your Zoom pencil to draw all the potential components on the following.  fyi - this is from an actual interview take-home I did from my last company.  Tip: This could also help with your assignment. 

<img src="/assets/weather.png">

---
transition: slide-left
---

# Exercise: Draw components (pg.2)
Use your Zoom pencil to draw all the potential components on the following images

- In breakout groups, take 10 minutes to draw potential components in the following designs

1. [Payment page](https://ebizcharge.com/wp-content/uploads/2022/06/Tarlet-Payment-Page.png)
1. [LinkedIn Learning Courses page](https://spotlight.lehigh.edu/sites/spotlight.lehigh.edu/files/Screen%20Shot%202020-08-14%20at%2010.32.20%20AM_0.png)
1. [Dashboard](https://assets.justinmind.com/wp-content/uploads/2020/02/dashboard-design-example-hcare.png)

---
transition: slide-left
---

# Exercise: Create simple React component
25 mins

- Create a component called `<FollowPerson>`
- reminder: all React components have to start with a Capital Letter
- see https://tachyons.io/components/lists/follower-notifications/index.html

   <img src="/assets/inbox.png" />

- What props do you think we'll need for this component?
- What other potential components could be developed/imported inside `<FollowPerson>` component?

---
transition: slide-left
---

# Iteration
to make lists, simply use the vanilla JS array method .map.  

```jsx
const PeopleList = () => {
  return (
    <div>
      <h2>People to Follow</h2>
      { 
        people.map(person => (
          <FollowPerson
            key={ person.id } // notice we use key
            name={ person.name }
            username={ person.username }
            followHandler={() => console.log('clicked follow button')}
          />
        ))
      }
    </div>
  );
};
```

---
transition: slide-left
---

# Exercise: Lists 
10 mins

- create a list via `.map()` to make at least 3 `<FollowPerson>` components
- Make up your own array of people data

<img src="/assets/list1.png" style="height: 300px">


---
transition: slide-left
---

# Optional: Configure imports to use absolute path

- Use ChatGPT to help you configure your tsconfig.json, tsconfig.app.json, vite.config.ts
- ❌ Using relative paths can be a pain point, especially when refactoring locations of files/folders
- ✅ should now be able to use `import Component from '@/components/whatever' 

---
layout: image-right
transition: slide-left
image: /assets/dodds.png
backgroundSize: 400px 400px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:
- 📖 [Do you build FE or BE first?](https://www.codemzy.com/blog/build-front-end-or-back-end-first)
- 🧢 [React Crash Course](https://www.youtube.com/watch?v=LDB4uaJ87e0)
- 🗾 [Beginner's Guide to React](https://egghead.io/courses/the-beginner-s-guide-to-react)
- ⛰️ [Epic React](https://www.epicreact.dev/tutorials/get-started-with-react)
- 🎬 [Scrimba - Learn React](https://scrimba.com/learn-react-c0e)r

<br>
<hr>
<br>

- 🧪 [Enter anonymous lab questions](https://docs.google.com/forms/d/e/1FAIpQLSevvGARdHQikso-uLqFCO481MABKE5HofuSrlzEPMNQ2ZLykw/viewform?usp=dialog)
- ℹ️ [Course feedback survey](https://circuitstream.typeform.com/to/ZoyYk7px#course_id=SoftwareAN&instructor=9514)

---
transition: slide-left
---

# Conditionals

- in JSX, with the curly braces, we can't use JS statements, only expressions
  - why do you think we can't use JS statements?  (think what is being passed to `React.createElement()`? )
- use of `&&` 
  - ex: `{ isOnline && <div className="green" /> }`
  - why does the above work?  what's happening?
  - ex: `{ numOfItems > 0 && <ShoppingList items={shoppingList} /> }`
  - ex: `{ !!numOfItems && <ShoppingList items={shoppingList} /> }`
- use of ternary operators
  ```jsx
  return (
    <>
      { isLoggedIn ? <AdminDashboard /> : <p>Please login first</p> }
    </>
  )
  ```

---
transition: slide-left
---

# Exercise: Use conditional for a prop

- Modify your `<Button />` component such that if it is given the `disabled` prop, it will actually make the button disabled
   - reminder: can disable an HTML button tag via `<button disabled>Submit</button>`
`<Button label="Submit" disabled />`

---
transition: slide-left
---

# Exercise: Use conditional for text

<img src="/assets/inbox.png" style="width: 400px" />

- make it so that if variable `isFollowing` is true, then the button text will say `- Following`
   - otherwise if `isFollowing`is false, then button text will say `+ Follow`


---
transition: slide-left
---

# Homework

- Exercise: Create simple React website
   - Reverse engineer: convert this entire [Email template layout](https://pure-css.github.io/layouts/email/) to JSX; [Github code here](https://github.com/pure-css/pure/tree/main/site/static/layouts/email)
- Begin thinking about your "Weather Forecasting App" assignment due Aug 17 midnight EST