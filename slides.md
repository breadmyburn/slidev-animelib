---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://preview.redd.it/rtlehtomjpo51.jpg?width=1697&format=pjpg&auto=webp&s=7efa56b980e284c857ed38d3378075154001311a
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
---

# AnimeLib

An Anime Catalogue

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: image-right
image: https://preview.redd.it/rtlehtomjpo51.jpg?width=1697&format=pjpg&auto=webp&s=7efa56b980e284c857ed38d3378075154001311a
---

# What is AnimeLib?

- AnimeLib is an anime catalogue of people's favourite animes.

- Every user has a "Watchlist" where they can add animes they are interested in.

---

# What is currently used to build AnimeLib?

### Frontend

- React.js
- Vite.js
- Tailwind CSS

### Features

***Context API***
- Produces global variables that can be passed around.

***Lazy Loading (Code-Splitting)***
- Loads only the necessary parts of an aplication when they are required rather than loading all resources at the beginning.
- Improves performance and reduces loading times.

---

# What is currently used to build AnimeLib?

### Backend

- Spring Boot 2.3.12
- MyBatis-Plus
- MyBatisPlus-Plus
- Project Lombok

### Database

- MySQL
- Liquibase

### Miscellaneous
- Docker

---
layout: image-right
image: https://steamuserimages-a.akamaihd.net/ugc/763849701486576504/56894A65A59574D75D110B414CB20B8DD5D2308B/?imw=637&imh=358&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=true
---

# Project Structure in DDD (Backend)

```
main
├── java
│   └── com.sunognaisda.animelib
│       ├── application
│       │   └── rest
│       ├── domain
│       │   ├── mapper
│       │   ├── model
│       │   └── service
│       ├── impl
│       │   └── domain
│       │       └── service
│       └── AnimelibApplication.java
│
└── resources
    ├── db
    │   └── liquibase
    ├── mapper
    ├── application.properties
    └── mybatis-config.xml
```

---

# Database ERD

![0](/assets/images/erd.png)

---

# APIs

**Working**

- Register

**In-Progress**

- Login

---

# Future Implementation

- Apache Shiro
- Redisson
- Quartz
- JustAuth
- Hutool
- AutoPOI
- Knife4j

---

# References

- Lazy loading in React | LoginRadius Blog (https://www.loginradius.com/blog/engineering/lazy-loading-in-react/)

- A Guide to React Context and useContext() Hook (https://dmitripavlutin.com/react-context-and-usecontext/)

- Spring Boot 2.3.12 Reference Documentation (https://docs.spring.io/spring-boot/docs/2.3.12.RELEASE/reference/html/index.html)

- MyBatis和JPA的优劣以及MyBatis-Plus的使用 (https://blog.csdn.net/qq_45735705/article/details/115988506)

- MyBatis-Plus (https://baomidou.com/)

- MyBatisPlus-Plus (https://gitee.com/jeffreyning/mybatisplus-plus)

- mybatisplus 复合主键(多主键) CRUD (https://blog.csdn.net/virtual_users/article/details/118151385)

- Liquibase Documentation (https://docs.liquibase.com/home.html)
