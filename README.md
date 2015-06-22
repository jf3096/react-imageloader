react-imageloader
=================

One of the hardest things to wrangle in the browser is loading. When images and
other linked elements appear in the DOM, the browser makes decisions on when to
load them that sometimes result in problems for a site and its users, such as
[FOUC], unexpected load ordering, and degraded performance when many loads are
occurring.

This [React] component can improve the situation by allowing you to display
content while waiting for the image to load, as well as by showing alternate
content if the image fails to load.


Usage
-----

```javascript
import React from 'react';
import ImageLoader from 'react-imageloader';

function preloader() {
  return <img src="spinner.gif" />;
}

React.render((
  <ImageLoader
    src="/path/to/image.jpg"
    wrapper={div}
    preloader={preloader}>
    Image load failed!
  </ImageLoader>
), document.body);

```


Props
-----

<table>
  <thead>
    <th>Name</th>
    <th>Type</th>
    <th>Description</th>
  </thead>
  <tbody>
    <tr>
      <td><code>src</code></td>
      <td>string</td>
      <td>The URL of the image to be loaded.</td>
    </tr>
    <tr>
      <td><code>preloader</code></td>
      <td>function</td>
      <td>An optional React component class or function that returns a React
          element to be shown while the image loads.</td>
    </tr>
    <tr>
      <td><code>onLoad</code></td>
      <td>function</td>
      <td>An optional handler for the <code>[load]</code> event.</td>
    </tr>
    <tr>
      <td><code>onError</code></td>
      <td>function</td>
      <td>An optional handler for the <code>[error]</code> event.</td>
    </tr>
    <tr>
      <td><code>wrapper</code></td>
      <td>function</td>
      <td>A React component class or function that returns a React element
          to be used as the wrapper component. Defaults to <code>React.DOM.span</code>.</td>
    </tr>
  </tbody>
</table>


[FOUC]: http://en.wikipedia.org/wiki/FOUC/
[React]: http://facebook.github.io/react/
[load]: https://developer.mozilla.org/en-US/docs/Web/Events/load
[error]: https://developer.mozilla.org/en-US/docs/Web/Events/error
