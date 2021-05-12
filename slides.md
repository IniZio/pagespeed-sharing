---
theme: geist
image: https://unsplash.com/photos/Ca9GXrkOR98/download?force=true
---

# Pagespeed Hell

A journey in 🏘 **Village**

<div class="pt-12">
  Newman
</div>


<!--
Hello, last several weeks we have been talking about things that have clear answers, for example
all hail Tailwind, mind your pixels. This week we are gonna talk about something different, the Pagespeed hell
-->

---

# Village?

>  Local communities coming together to buy, sell & help

<br />

<v-clicks>

- 📱 **Mobile App** for end-users
- 🔋 Server-side rendered **Website** for SEO
- 🤔 Wanted to improve **PageSpeed** score

</v-clicks>

---

- Boosted PageSpeed score to **70+** on mobile and **90+** on desktop...

<div class="flex w-full gap-2">
  <Image class="flex-1 min-w-0" src="../assets/pagespeedv5-mobile.png" />
  <Image class="flex-1 min-w-0" src="../assets/pagespeedv5-desktop.png" />
</div>

- ...then suddenly plummeted <Image class="inline" width="40" src="../assets/sadfrog.png" />

<div class="flex w-full gap-2">
  <Image class="flex-1 min-w-0" src="../assets/pagespeedv7-mobile.png" />
  <Image class="flex-1 min-w-0" src="../assets/pagespeedv7-desktop.png" />
</div>

---
layout: section
---

# PageSpeed

- How fast does **Google** think your website is

<Image class="mx-auto h-[80vh] filter drop-shadow-lg" src="../assets/google-io-pagespeedv7-mobile.png" />

---
layout: section
---

# Why it matters

- 🤔 Points out critical issues from **user** perspective
- 🖥 No more **"But it loads fast from my desktop!"** excuse

<div class="mx-auto h-80 w-[80vw] overflow-y-scroll scrollbar-thin">
<a class="block" href="https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fevents.google.com%2Fio" target="_blank">
  <Image class="mx-auto w-[80vw] filter drop-shadow-lg" src="../assets/google-io-pagespeedv7-mobile.png" />
</a>
</div>

---

# Metrics

<br />

| Name        | Description           | Weight  |
| ------------- |:-------------| -----:|
| **First Contentful Paint** (FCP)     | First element appears on screen | 20% |
| **Speed Index** (SI)     | Sum of render time of every element on screen    | 27% |
| **First Meaningful Paint** (LCP) | Most meanful elements appear on screen |  7% |
| **Time to Interactive** (TTI) | When most elements actually reacts | 44% |
| **First CPU Idle** (FCI) | When anything is interactive | 13% |

---

# Metrics

<div class="fixed right-0 w-[60vw]">
  <Image class="filter drop-shadow-lg" src="../assets/pagespeed-metrics.png" />
</div>

<br />

| Name        | Description           | Weight  |
| ------------- |:-------------| -----:|
| **First Contentful Paint** (FCP)     | First element appears on screen | 20% |
| **Speed Index** (SI)     | Average speed of all elements on screen    | 27% |
| **First Meaningful Paint** (LCP) | Most meanful elements appear on screen |  7% |
| **Time to Interactive** (TTI) | When most elements actually reacts | 44% |
| **First CPU Idle** (FCI) | When anything is interactive | 13% |

---

# Day 0

<br>

<div class="mx-auto h-98 w-[80vw] overflow-y-scroll scrollbar-thin">
  <Image class="mx-auto w-[80vw] filter drop-shadow-lg" src="../assets/pagespeedv5-day-0.png" />
</div>

---

# Step 0

<br />

- 🏗 **Basic infra** e.g. CDN abnormal...✅
- 🔥 **Server stable**...✅
- 🚔 **Sentry errors**...✅
- 🤺 Have a **10-minute** sword fight between each build...?!

---

# Things to improve

<br />

- 👨‍🍳 **Build tools** - Webpack (+ Babel)
- 🖼 **Asset optimizations**
- 💤 **Lazyload** - Code-splitting
- 🤥 **3rd party elements** - Blocks TTI

---

# Build tools

### Upgrade from Webpack v1 to v4

<br />

- 🌲 **Tree-shaking** - Bundle analyzer, `babel-plugin-import`
- ♻ `nodemon` + live-reload

<div class="pt-12" />

- -> Bundle size reduced from 5MB to 2MB (gzipped)
- -> Build time reduced to ~2-3 minutes first build, 30s consecutive builds

---

# Assets optimizations

> Always need fallback in Safari

- **Modern media formats** - GIF -> Webm and MP4, JPEG -> Webp
- **Lazyload** - HTML's `lazy`, `onLoad`

---

# Lazyload

- **Code-splitting** - `@loadable/component`
- **Dynamic import** - 


---
layout: center
class: text-center
---

# Q&A
