# backbone

A Vue 3 playground (Vue CLI 4, Vuex 4, Vue Router 4, Quasar 2) where each route demos one UI library or app feature.

## Demo views

| Route | View | What it shows |
|-------|------|---------------|
| `/` | `Home.vue` | the Vue CLI welcome component |
| `/bootstrap` | `Bootstrap.vue` | responsive layout blocks with Bootstrap 5 |
| `/owl` | `OwlCarousel.vue` | an Owl Carousel slider with its full option set (jQuery plugin) |
| `/aos` | `AnimateOnScroll.vue` | columns that animate in with AOS while scrolling |
| `/odometer` | `OdoMeterJs.vue` | animated number counters with odometer |
| `/fullpage` | `FullPageJs.vue` | full-screen section scrolling with fullPage.js |
| `/api` | `Apis.vue` | meetups CRUD against a REST backend through Vuex and axios |
| `/auth` | `Auth.vue` | login, signup and forgot-password forms backed by the Vuex auth module |
| `/reset-password/:token` | `Auth.vue` | currently renders the auth forms; the dedicated `RestorePasswordView.vue` is not routed yet |

## Backend

The auth module calls the backend at `VUE_APP_BASE_URL_BACK` (see `.env`, default `http://localhost:1337/`).

## Node version

The build uses webpack 4, so on Node 17+ run it with `NODE_OPTIONS=--openssl-legacy-provider`.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Installed Packages 


+ bootstrap@5.1.0
+ owl.carousel@2.3.4
+ jquery@3.6.0
+ @popperjs/core@2.9.3
+ animate.css@4.1.1
+ @fortawesome/fontawesome-free@5.15.4
