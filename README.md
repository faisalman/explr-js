# Explr.js

Explorer-like tree jQuery plugin

## Usage

```html
<!-- include the required CSS -->
<link rel="stylesheet" type="text/css" href="jquery.explr.css" />
                
<!-- include any version of jQuery before including plugin -->
<script type="text/javascript" src="jquery-1.7.1.min.js"></script>

<!-- include the plugin -->
<script type="text/javascript" src="jquery.explr-1.1.min.js"></script>

<ul class="explr">
    <li>
    <a href="#">1st item 1st level</a>
    <ul>
        <li>
        <a href="#">1st item 2nd level</a>
        </li>
    </ul>
    </li>
    <li>
    <a href="#">2nd item 1st level</a>
    </li>
</ul>

<script type="text/javascript">
$('.explr').explr();
</script>
```

### Options

| option | type | default | description |
| --- | --- | --- | --- |
| `ajaxContainerId` | `string` | `"explr-content"` | id element of AJAX container |
| `ajaxLoadingText` | `string` | `"<p>loading data..</p>"` | HTML to be displayed when loading AJAX request |
| `ajaxOptions` | `object` | `{}` | See `$.ajax()` API reference |
| `animDuration` | `string` | `"fast"` | Duration of toggle animation, set 0 to disable |
| `folderTooltip` | `string` | `"click to expand/collapse"` | Tooltip to be displayed when mouse hover the folders |
| `rememberState` | `bool` | `true` | Store tree state in cookie |
| `startCollapsed` | `bool` | `true` | Collapsed/expanded at start |
| `treeHeight` | `string` / `number` | `"auto"` | Height of tree in number (of pixels) or 'auto' to adjust automatically |
| `treeWidth` | `string` / `number` | `"auto"` | Width of tree in number (of pixels) or 'auto' to adjust automatically |

Example:

```js
$('.explr').explr({
    startCollapsed : true,
    treeHeight : 200,
    treeWidth : 400
});
```

To load AJAX content when clicking node, add `rel="explr-ajax"` attribute to the link elements like this:

```html
<div class="tree-wrapper">
    <ul id="id">
    <li>
        <a href="#">External content loaded with AJAX</a>
        <ul>
        <li>
            <a href="test.html" rel="explr-ajax">load test.html</a>
        </li>
        <li>
            <a href="test.php?getdata=hello" rel="explr-ajax">load test.php along with a GET data</a>
        </li>
        </ul>
    </li>
    <li>
        <a href="#">Internal content</a>
        <ul>
        <li>
            <a href="#top">go to top of page</a>
        </li>
        <li>
            <a href="#bottom">go to bottom of page</a>
        </li>
        </ul>
    </li>
    </ul>
</div>

<div id="ajax-content-wrapper"></div>

<script type="text/javascript">
$('.tree-wrapper').explr({
    ajaxContainerId	: 'ajax-content-wrapper'
});
</script>
```

### Icons

| ![](css/img/pc.de/address.png) icon-address | ![](css/img/pc.de/address.png) icon-archives | ![](css/img/pc.de/bestseller.png) icon-badge | ![](css/img/pc.de/address.png) icon-bank | ![](css/img/pc.de/address.png) icon-basket | ![](css/img/pc.de/order.png) icon-board |
| --- | --- | --- | --- | --- | --- |
| icon-board2 | icon-book | icon-bookmark | icon-business | icon-calendar | icon-card |
| icon-card2 | icon-chain | icon-chart | icon-lock | icon-check | icon-clock |
| icon-comment | icon-config | icon-customers | icon-cv | icon-direction | icon-flag |
| icon-folder | icon-folder2 | icon-folder3 | icon-hand | icon-heart | icon-help |
| icon-home | icon-lamp | icon-left | icon-left2 | icon-mail | icon-mail2 |
| icon-palette | icon-pencil | icon-pencil2 | icon-phone | icon-photo | icon-print |
| icon-project | icon-refresh | icon-right | icon-right2 | icon-star | icon-tag |
| icon-text | icon-text2 | icon-text3 | icon-text4 | icon-user | icon-world |
| icon-zoom ||||||

To define another custom icon class name you have to edit the CSS file, then add a CSS class preceded by `.explr-tree` like this:

```css
.explr-tree .icon-mycustomicon > li, .explr-tree li.icon-mycustomicon {
    background-image: url("img/mycustomicon.png");
}
```

## Credits

* Stuttgart icon set from PC.DE

## License

Dual licensed under GPLv2 & MIT

Copyright © 2010-2011 Faisal Salman <<f@faisalman.com>>

Permission is hereby granted, free of charge, to any person obtaining a copy of 
this software and associated documentation files (the "Software"), to deal in 
the Software without restriction, including without limitation the rights to use, 
copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the 
Software, and to permit persons to whom the Software is furnished to do so, 
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all 
copies or substantial portions of the Software.