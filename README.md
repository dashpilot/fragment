# Fragment Function

The `fragment` function is a JavaScript utility designed to enhance web pages with Single Page Application (SPA)-like behavior. It intercepts link clicks on elements with the `data-fragment` attribute, fetches the content from the specified URL, and updates a specific part of the page without reloading. Additionally, it updates the browser's history and document title, and emits a custom event for further integration.

## Features

-   **Dynamic Content Loading**: Fetches and updates content for a specified fragment ID from the clicked link's URL.
-   **Active Link Highlighting**: Manages active state for links with the `data-fragment` attribute.
-   **Browser History Management**: Updates the URL in the address bar and the browser's history stack.
-   **Title Update**: Extracts and updates the document title from the fetched content.
-   **Custom Event Emission**: Emits a `fragment:loaded` event after content is loaded and the URL is updated, allowing for additional custom logic.

## Usage

### HTML Structure

Ensure your links have the `data-fragment` attribute and point to the desired URL:

```html
<a href="page1.html" data-fragment="main">Page 1</a>
<a href="page2.html" data-fragment="main">Page 2</a>
<div id="main">
    <!-- Content will be dynamically loaded here -->
</div>
```

### Listening for the Custom Event

You can hook into the `fragment:loaded` event to perform additional actions:

```javascript
document.addEventListener('fragment:loaded', function (e) {
    console.log('Fragment loaded for URL:', e.detail.url);
    console.log('Updated fragment ID:', e.detail.fragmentId);
    // Add your custom logic here
});
```

## Conclusion

The `fragment` function provides a simple way to implement SPA-like behavior on your website, enhancing user experience by dynamically loading content and managing browser history. Customize and extend it to fit your specific needs.