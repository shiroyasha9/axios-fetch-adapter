# Why

I had been using [@vespaiach/axios-fetch-adapter](https://github.com/vespaiach/axios-fetch-adapter) for a while and it worked well. However, it's not maintained anymore and I needed it to be compatible with the latest version of Axios. So I decided to fork it and make it work with axios@1+.

Axios doesn't have an adapter for fetch API for now. So you can use this adapter for services that require fetch API (looking at you `contentful` 😒).

# Installation and Usage

You can install the adapter directly from this repository URL or feel free to copy its source code to your project. Can use npm/yarn/bun/whatever you like.

```sh
npm install axios
npm install @shiroyasha9/axios-fetch-adapter
```

There are two ways to use it:

1.  Create a new instance of Axios and pass this adapter in configuration

```js
const instance = axios.create({
  baseURL: 'https://some-domain.com/api/',
  timeout: 1000,
  adapter: fetchAdapter
  ....
});
```

2.  Pass this adapter in each of request

```js
axios.request({
  url: '/user',
  method: 'get',
  adapter: fetchAdapter
  ...
})
```

3.  Use with FormData

```js
axios.request({
  url: '/user',
  method: 'post',
  adapter: fetchAdapter
  data: new FormData(formId)
  ...
})
```

# Note

- Since, this adapter relies on fetch API so it won't work in Node environment
- Feel free to report any issues and I'll try to fix them!
