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
- [ ] Iteration
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
10 mins

- In breakout groups, take 10 minutes to draw potential components in the following designs
- Use your Zoom pencil to draw all the potential components on the following images

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
- Can copy/paste JSON data from https://randomuser.me/

<img src="/assets/list1.png" style="height: 300px">


---
layout: image-right
transition: slide-left
image: /assets/swyx.png
backgroundSize: 400px 450px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:

- 🎮 [React video game](https://www.youtube.com/watch?v=m8SmXOTM8Ec#t=0m28s)
- 🥊 [React vs Vue vs Angular](https://www.youtube.com/watch?v=_licnRxAVk0)
- ⚛️ [React Conf 2024 Recap](https://www.youtube.com/watch?v=udXZw-9LdOM)
- ▶️ [React vs Vue: ASync state, effects, hooks](https://www.youtube.com/watch?v=WhE2y3J45CM)

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
5 mins. Continuing with your first iteration of this component from an earlier slide...

- Modify your `<Button />` component such that if it is given the `disabled` prop, it will actually make the button disabled
   - reminder: can disable an HTML button tag via `<button disabled>Submit</button>`
`<Button label="Submit" disabled />`

---
transition: slide-left
---

# Exercise: Use conditional for text
5 mins. Continuing with your first iteration of this component from an earlier slide...

<img src="/assets/inbox.png" style="width: 400px" />

- make it so that if variable `isFollowing` is true, then the button text will say `- Following`
   - otherwise if `isFollowing`is false, then button text will say `+ Follow`


---
transition: slide-left
---

# Exercise: Create simple React website
remainder of time.  Choose one appropriate to your comfort level so far with React

Level 1
- Convert this [menu design](https://miro.medium.com/v2/resize:fit:600/1*Xnksl3Gt8jsztClkLKMpZQ.png) into React/JSX OR convert your HTML/CSS Assignment 1 into React/JSX

Level 2
- Convert this entire [Email template layout](https://pure-css.github.io/layouts/email/) to React/JSX; [Github code here](https://github.com/pure-css/pure/tree/main/site/static/layouts/email)

Level 3
- Convert this entire [Dashboard](https://assets.justinmind.com/wp-content/uploads/2020/02/dashboard-design-example-hcare.png) to React/JSX

---
transition: slide-left
---

# Homework

- Finish converting to JSX [Email template layout](https://pure-css.github.io/layouts/email/) to JSX; [Github code here](https://github.com/pure-css/pure/tree/main/site/static/layouts/email)
- Begin thinking about your "Weather Forecasting App" assignment due Aug 17 midnight EST