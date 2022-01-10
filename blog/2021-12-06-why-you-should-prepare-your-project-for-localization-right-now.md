---
slug: why-you-should-prepare-your-project-for-localization-right-now

title: 🌎 Why you should prepare your project for localization (i18n) right now

author: Jan Cizmar 😎

author_title: Tolgee CTO

author_url: https://github.com/JanCizmar
author_image_url: https://avatars.githubusercontent.com/u/18496315?v=4
tags: [webdev, javascript]
---

We always recommend preparing projects for localization as soon as possible. A lot of people, we are talking
with, say that they are in early stage of development of their app and localization 🌎 is something they don't need
right now.

Setting localization aside is not a good idea, and I am going to tell you why.

<!--truncate-->

## It's boring and repetitive task ⌛🔄

When localizing your application with a lot of strings already in code, the localization is going to be very painful 🩸
task. In that case you will have to go through all your code and wrap all the strings in the code with some component or
method, depending on language or framework you use. This could be hundreds or thousands of strings to wrap and
localization keys to come up with.

See this example:

```html
<h1>My beautiful App</h1>

<button>Like it!</button>
```

We have a tiny little app with a headline and button, whatever the button does, it has a text in it. It has a text to be
translated! 😎 To translate it we have to transform it to something like this.

```html

<h1>
  <T key="my-app-headline">My beautiful App</T>
</h1>

<button>
  <T key="button-like">Like</T>
</button>
```

Think of the `T` element as something which is replacing the text with translated value when language changes.

Now imagine, you have a code with thousands of strings like this you have to go through and wrap every text with this
kind of code. It's very hard to do something like this with find & replace tool, since you have to come up with the nice
semantic key.

## Missing strings 🎯

Going through your codebase and replacing all the strings is not that easy as it seems, there could be translations in
the element content, in the attributes, it could be generated by the logic and provided though variables or function
calls.

```html
<h1 id="headline"></h1>
<script>
  const headline = document.getElementById("headline");
  if (isTheAppCool) {
    headline.textContent = "My cool App"
  } else {
    headline.textContent = "My App"
  }
</script>
```

What now? 🙈 While this code is provided in the script part, it's very simple to miss it and provide imperfect
experience to your users.

## Losing context

When translating the application to different languages, you'll probably reach a point, when you would like translators
to translate your app. So you take localization data from your app and send them to translators. Then you expect perfect
results, since you don't understand the foreign language. That's the reason, why you pay for translator, isn't it?

So you will provide file like this.

```json title="en.json"
{
  "my-app-headline": "My beautiful App",
  "button-like": "Like"
}
```

But the translator don't have any context information about the texts. Where is it on the page? What's the purpose of the
button? What is the gender of the objects? Is this noun or verb?

## How can you do better?

Simple. Just integrate localization as soon as possible. From the beginning prepare your app to be localized. As a
Tolgee founder I would recommend you to use out solution 😁, but you can use any other library suitable for your
framework or language.

- React: `react-intl`, `react-i18next` or [`@tolgee/react`](https://tolgee.io/integrations/react)
- Vue: `vue-i18next`, `vue-intl` or [`@tolgee/vue`](https://tolgee.io/integrations/vue)
- Angular: `@angular/localize` (native), `angular-i18next`, [`@tolgee/angular`](https://tolgee.io/integrations/angular)
- Svelte: `svelte-i18n`, [`@tolgee/svelte`](https://tolgee.io/integrations/svelte)

While using those tools, try to also store context of the keys in form of comments or screenshots, which you can provide
to translators in the future.

### How can Tolgee 🐁 help?

Preparing your app to be localized is always good idea and with Tolgee you can do it without much time cost, since your
only task is to wrap the string with T component come up with a nice translation key. Then you can just go to your app
and translate your string with `ALT + Click`. You can also automatically generate a screenshot from your App to provide
the context to your future translators. If you would like to learn more about it,
check [our documentation 📚](https://tolgee.io/docs) or choose an integration library above and follow the tutorials. 📖 

## TL; DR

- Prepare your app for localization now 😎
- You'll avoid untranslated texts 🥳
- Your page will be translated correctly ✅
- You will not die due to bore of the repetitive replacing your strings ⚰️⚱️

If you like what we do, please star our GitHub projects. 🙏

- [Tolgee Server](https://github.com/tolgee/server) ⭐
- [Tolgee JS](https://github.com/tolgee/tolgee-js) ⭐