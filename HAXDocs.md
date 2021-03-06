# HAX Configuration UI

This allows you to configure HAX and the available elements for your content contributors Select your CDN and enable the elements you'd like exposed to editors when they use HAX. You can also switch between CDNs or run your own copies of assets locally to include custom elements you've made!

## Getting help
- [HAX Slack](https://join.slack.com/t/elmsln/shared_invite/enQtMjg2MzUxMTYyNjcyLWNhYzU1ODk0MjQ5MWZlNjVjNWJkMmZlODJiMGNmNDBjODk2NDc2MDUzNTZkODE4NTRiMjUzYzkzOTBkNjI4NGE) - where HAX core developers talk web components / all our projects
- [HAX Issue Queue](https://github.com/elmsln/issues/issues) - Unified issue queue for all of our projects
- [HAXCamp: Uncode](http://bit.ly/haxuncode) - Friday 3-5pm EST weekly recorded hang out to discuss web components, hax and answer community questions. Join our slack to confirm air dates. [Watch past episodes here](https://www.youtube.com/channel/UCgcFR9ojBu9P7VNQjt0nqbA/videos)
- [#HAXTheWeb on twitter](https://twitter.com/search?q=%23HAXTheWeb&src=typed_query&f=live) - 
- [Web components Slack](https://www.polymer-project.org/slack-invite) - A very popular open hang out for web component developers. (Named polymer but not polymer specific)

## Developers
You can run and build assets local to your project as opposed to using one of the zero-config CDNs (or use your own!). CDN providers are created using the following tools:
- [Unbundled Webcomponents repo](https://github.com/elmsln/unbundled-webcomponents) - Using this can you can make your own build that works in HAX and any other website with relative ease. The tooling is all preconfigured, all you need to do is install new assets from NPM (use yarn to do this) and 
- [OpenWC](https://open-wc.org/) - While not HAX related, this is a great community tooling repo to get started with web components and front end development using best practices.
- [WCFactory](https://github.com/elmsln/wcfactory) - This can be used to build and manage a web components repo at scale. This is a meta tooling which can be used to build a monorepo using best practices of managing and deployment hundreds of elements. This is what the HAX core team uses to build and manage [LRNWebComponents](https://github.com/elmsln/lrnwebcomponents).
- [lit-element docs](https://lit-element.polymer-project.org/) - While not required, LitElement is a very popular base case for development web components that provides better DX than "VanillaJS" while still being extremely small.

## Wiring custom elements to HAX
All you need to do for your element to work with HAX is add a `static get haxProperties()` function on your element which returns HAXSchema. You can read up on [HAXschema on HAXTheWeb.org](https://haxtheweb.org/hax-schema). Schema is relatively simple to construct (honestly we usually [copy and paste from existing elements](https://github.com/elmsln/lrnwebcomponents/blob/master/elements/video-player/src/video-player-hax.json) and tweak values).

The HAX core team builds in a mix of LitElement and VanillaJS and recommends everyone start at LitElement when working with HAXSchema though because of the web component standard HAX works with ANY web component library!