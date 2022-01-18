# Repo to demonstrate a next/image bug

## Installation

```
git clone git@github.com:inside/next-image-app.git
cd next-image-app
npm install
npm run build && npm start
```

## Steps To Reproduce

1. Open this image in your browser:
   [`http://localhost:3000/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fmountains.a2eb1d50.jpg&w=1920&q=75`](http://localhost:3000/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fmountains.a2eb1d50.jpg&w=1920&q=75)
   => This is ok

1. Now open this noexistent image in your browser (the word "mountains" from the above url has been renamed to "foo"): [`http://localhost:3000/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Ffoo.a2eb1d50.jpg&w=1920&q=75`](http://localhost:3000/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Ffoo.a2eb1d50.jpg&w=1920&q=75)
   => This is not ok. The browser hangs for a long time and eventually returns a `504` http error
