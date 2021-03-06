jQuery AutoLink
=====

jQuery AutoLink is a jQuery plugin for automatically converting text containing URLs, mentions (for Twitter, Instagram, GitHub, or a locally hosted site) and hashtags (for Twitter or a locally hosted site) into URLs. It automatically transforms plain text URLs, mentions, & hashtags into clickable URLs.

## Changes

This fork (<a href="https://github.com/MarQuisKnox/jQuery.AutoLink">@MarQuisKnox/jQuery.AutoLink</a>) of [Linky](https://github.com/AnSavvides/jquery.linky) has the following changes:
<br><br>
1. Adds the option to link locally<br>
2. Adds the option to specify the href target<br>
3. Adds e-mail autolinking<br>
4. Fixes YouTube Embeds<br>
5. Fixes URL RegEx<br>
6. Matches URLs w/ Parameters<br>
7. Matches all TLDs except for those w/ unicode characters

## Usage

The only dependency is [jQuery](http://jquery.com/).

All you have to do is include [`jquery.autolink.js`](jquery.linky.js) or [`jquery.autolink.min.js`](jquery.autolink.min.js) just after you've included `jQuery` and you're all set.

### Options
| Option        | Default     | Type         | Description |
| ------------- |:-----------:| ------------:| -----------:|
| emails      | `true`     | `boolean`    | Identify if e-mail addresses should be linkified. |
| mentions      | `true`     | `boolean`    | Identify if mentions should be linkified. |
| hashtags      | `false`     | `boolean`    | Identify if hashtags should be linkified. |
| urls          | `true`      | `boolean`    | Identify if URLs should be linkified. |
| linkTo        | `"twitter"` |  `string`    | Identify location mentions and hashtags should link to.|

### Example

jQuery AutoLink would come in handy if you are pulling data from any of Twitter's or Instagram's APIs where you will end up having just a plain text string like below:

`@andreassavvides works on his #opensource projects over at https://github.com/AnSavvides`

If you are displaying this information in your UI, you would want to linkify any mentions, hashtags and/or URLs. Linky does exactly that, giving you control over what you want linkified. In this case, let's linkify everything given a `div` containing the aforementioned tweet:

```html
<div class="status">
    @andreassavvides works on his #opensource projects over at https://github.com/AnSavvides        
</div>
```

```js
$(".status").autolink({
    mentions: true,
    hashtags: true,
    urls: true,
    linkTo: "local"
});
```

This would transform the `div`'s content to the following:

```html
<div class="url">
    <a href="https://twitter.com/andreassavvides" target="_blank">@andreassavvides</a> works on his <a href="https://twitter.com/search?q=opensource" target="_blank">#opensource</a> projects over at <a href="https://github.com/AnSavvides" target="_blank">https://github.com/AnSavvides</a>
</div>
```

Have a look at [examples.html](examples.html) for more examples.

## Tests
Unit testing is done using [QUnit](http://qunitjs.com/); all tests can be found under the [tests](tests) folder.

## Contributing
All contributions are welcome; just fork the repository, make your changes and open a pull request. Don't forget to add tests if applicable!

## License
The MIT License (MIT)

Copyright (c) 2013 - 2015 Andreas Savvides<br>
Copyright (c) 2014 - 2017 MarQuis Knox

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
