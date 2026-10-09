<div align="center">
	<br>
	<br>
	<img width="360" src="media/logo.svg" alt="Got">
	<br>
	<br>
	<br>
	<br>
	<hr>
	<p>
		<p>
			<sup>
				Sindre's open source work is supported by the community.<br>Special thanks to:
			</sup>
		</p>
		<br>
		<br>
		<a href="https://www.fame.fi#gh-light-mode-only">
			<img src="https://sindresorhus.com/assets/thanks/fame-logo-light.svg" width="200" alt="Fame Helsinki">
		</a>
		<a href="https://www.fame.fi#gh-dark-mode-only">
			<img src="https://sindresorhus.com/assets/thanks/fame-logo-dark.svg" width="200" alt="Fame Helsinki">
		</a>
		<br>
		<br>
		<br>
		<br>
		<a href="https://depot.dev?utm_source=github&utm_medium=sindresorhus">
			<div>
				<picture>
					<source width="180" media="(prefers-color-scheme: dark)" srcset="https://sindresorhus.com/assets/thanks/depot-logo-dark.svg">
					<source width="180" media="(prefers-color-scheme: light)" srcset="https://sindresorhus.com/assets/thanks/depot-logo-light.svg">
					<img width="180" src="https://sindresorhus.com/assets/thanks/depot-logo-light.svg" alt="Depot logo">
				</picture>
			</div>
			<b>Fast remote container builds and GitHub Actions runners.</b>
		</a>
		<br>
		<br>
		<br>
	</p>
	<hr>
	<br>
	<br>
	<br>
	<br>
	<br>
	<br>
	<br>
</div>

> Human-friendly and powerful HTTP request library for Node.js

[![Downloads](https://img.shields.io/npm/dm/got.svg)](https://npmjs.com/got)
[![Install size](https://packagephobia.com/badge?p=got)](https://packagephobia.com/result?p=got)

[See how Got compares to other HTTP libraries](#comparison)

---

**You probably want [Ky](https://github.com/sindresorhus/ky) instead, by the same people. It's smaller, works in the browser too, and is more stable since it's built on [`Fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). Or [fetch-extras](https://github.com/sindresorhus/fetch-extras) for simple needs.**

---

**Support questions should be asked [here](https://github.com/sindresorhus/got/discussions).**

## Install

```sh
npm install got
```

**Warning:** This package is native [ESM](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) and no longer provides a CommonJS export. If your project uses CommonJS, you will have to [convert to ESM](https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c). Please don't open issues for questions regarding CommonJS / ESM.

**Got v11 is no longer maintained and we will not accept any backport requests.**

## Take a peek

**A [quick start](documentation/quick-start.md) guide is available.**

### JSON mode

Got has a dedicated option for handling JSON payload.\
Furthermore, the promise exposes a `.json<T>()` function that returns `Promise<T>`.

```js
import got from 'got';

const {data} = await got.post('https://httpbin.org/anything', {
	json: {
		hello: 'world'
	}
}).json();

console.log(data);
//=> {"hello": "world"}
```

For advanced JSON usage, check out the [`parseJson`](documentation/2-options.md#parsejson) and [`stringifyJson`](documentation/2-options.md#stringifyjson) options.

**For more useful tips like this, visit the [Tips](documentation/tips.md) page.**

## Highlights

- [Used by 10K+ packages and 5M+ repos](https://github.com/sindresorhus/got/network/dependents)
- [Actively maintained](https://github.com/sindresorhus/got/graphs/contributors)
- [Trusted by many companies](#widely-used)

## Documentation

By default, Got will retry on failure. To disable this option, set [`options.retry.limit`](documentation/7-retry.md#retry) to 0.

#### Main API

- [x] [Promise API](documentation/1-promise.md)
- [x] [Options](documentation/2-options.md)
- [x] [Stream API](documentation/3-streams.md)
- [x] [Pagination API](documentation/4-pagination.md)
- [x] [Advanced HTTPS API](documentation/5-https.md)
- [x] [HTTP/2 support](documentation/2-options.md#http2)
- [x] [`Response` class](documentation/3-streams.md#response-2)

#### Timeouts and retries

- [x] [Advanced timeout handling](documentation/6-timeout.md)
- [x] [Retries on failure](documentation/7-retry.md)
- [x] [Errors with metadata](documentation/8-errors.md)

#### Advanced creation

- [x] [Hooks](documentation/9-hooks.md)
- [x] [Instances](documentation/10-instances.md)
- [x] [Progress events & other events](documentation/3-streams.md#events)
- [x] [Plugins](documentation/lets-make-a-plugin.md)
- [x] [Compose](documentation/examples/advanced-creation.js)

#### Cache, Proxy and UNIX sockets

- [x] [RFC 7234 compliant caching](documentation/cache.md)
- [x] [Proxy support](documentation/tips.md#proxying)
- [x] [Unix Domain Sockets](documentation/2-options.md#enableunixsockets)

#### Integration

- [x] [Diagnostics Channel](documentation/diagnostics-channel.md)
- [x] [TypeScript support](documentation/typescript.md)
- [x] [AWS](documentation/tips.md#aws)
- [x] [Testing](documentation/tips.md#testing)

---

### Migration guides

- [Request migration guide](documentation/migration-guides/request.md)
  - [*(Note that Request is unmaintained)*](https://github.com/request/request/issues/3142)
- [Axios](documentation/migration-guides/axios.md)
- [Node.js](documentation/migration-guides/nodejs.md)

## Got plugins

- [`got4aws`](https://github.com/SamVerschueren/got4aws) - Got convenience wrapper to interact with AWS v4 signed APIs
- [`gh-got`](https://github.com/sindresorhus/gh-got) - Got convenience wrapper to interact with the GitHub API
- [`gl-got`](https://github.com/singapore/gl-got) - Got convenience wrapper to interact with the GitLab API
- [`gotql`](https://github.com/khaosdoctor/gotql) - Got convenience wrapper to interact with GraphQL using JSON-parsed queries instead of strings
- [`got-fetch`](https://github.com/alexghr/got-fetch) - Got with a [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) interface
- [`got-scraping`](https://github.com/apify/got-scraping) - Got wrapper specifically designed for web scraping purposes
- [`got-ssrf`](https://github.com/JaneJeon/got-ssrf) - Got wrapper to protect server-side requests against SSRF attacks
