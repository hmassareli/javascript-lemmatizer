JavaScript Lemmatizer
====

JavaScript Lemmatizer is a lemmatization library for JavaScript to retrieve a base form from an inflected form word in English. 

Inspired by [Ruby Lemmatizer](https://github.com/yohasebe/lemmatizer) but the returned values and the algorithm are different from it.

## Requirements

JavaScript Lemmatizer depends on the following libraries.

- [jQuery](http://jquery.com/)
- [Underscore.js](http://underscorejs.org/)

## Check

The operation check of JavaScript Lemmatizer is conducted in the following web browsers with Mac OS X.

- Firefox 35.0
- Google Chrome 40.0
- Safari 6.1.6
- Opera 25.0

## Install
######1. Download and unzip JavaScript Lemmatizer, and then put it in your project.

Directories of dict, js and vendor in JavaScript Lemmatizer are must, so you can put it in your project like this.

```
your-project
├ index.html
├ libraries
    ├ javascript-lemmatizer
        ├ dict
        ├ js
        ├ vendor
```

######2. Load jQuery, Underscore.js and JavaScript Lemmatizer in your HTML like the following code.

```html
<script src="libraries/javascript-lemmatizer/vendor/js/jquery.js"></script>
<script src="libraries/javascript-lemmatizer/vendor/js/underscore.js"></script>
<script src="libraries/javascript-lemmatizer/js/lemmatizer.js"></script>
```

Or you can load jQuery and Underscore.js the way you like.

######3. Use JavaScript Lemmatizer in your JavaScript code according to the Usage.

See also. [lemmatizer_sample.html](https://github.com/takafumir/javascript-lemmatizer/blob/master/html/lemmatizer_sample.html)

## Usage

You can use `Lemmatizer#lemmas` or `Lemmatizer#only_lemmas` methods like the follwoing sample in your JavaScript code.

```javascript
// initialize Lemmatizer.
var lemmatizer = new Lemmatizer();

// retrieve a lemma with a part of speech.
lemmatizer.lemmas('desks',  'noun');   // => [ ['desk', 'noun'] ]
lemmatizer.lemmas('talked', 'verb');   // => [ ['talk', 'verb'] ]
lemmatizer.lemmas('better', 'adj');    // => [ ['good', 'adj'] ]

// of course, available for irregular iflected form words.
lemmatizer.lemmas('went', 'verb');     // => [ ['go', 'verb'] ]
lemmatizer.lemmas('written', 'verb');  // => [ ['write', 'verb'] ]

// when multiple base forms are found, return all of them.
lemmatizer.lemmas('coded', 'verb');    // => [ ['cod', 'verb'], ['code', 'verb'] ]
lemmatizer.lemmas('leaves', 'noun');   // => [ ['leave', 'noun'], ['leaf', 'noun'] ]

// retrieve a lemma without a part of speech.
lemmatizer.lemmas('sitting');  // => [ ['sit', 'verb'] ]
lemmatizer.lemmas('oxen');     // => [ ['ox', 'noun'] ]
lemmatizer.lemmas('leaves');   // => [ ['leave', 'verb'], ['leave', 'noun'], ['leaf', 'noun'] ]

// retrieve only lemmas not including part of speeches in the returned value.
lemmatizer.only_lemmas('desks', 'noun');  // => [ 'desk' ]
lemmatizer.only_lemmas('coded', 'verb');  // => [ 'cod', 'code' ]
lemmatizer.only_lemmas('priorities');     // => [ 'priority' ]
lemmatizer.only_lemmas('leaves');         // => [ 'leave', 'leaf' ]
```

See also. [lemmatizer_sample.html](https://github.com/takafumir/javascript-lemmatizer/blob/master/html/lemmatizer_sample.html)

## Limitations
```javascript
// Lemmatizer leaves alone a word not included in it's dictionary index.
lemmatizer.lemmas('MacBooks', 'noun');  // => [ ['MacBooks', 'noun'] ]
```

## Contribution

1. Fork it ( https://github.com/takafumir/javascript-lemmatizer/fork )
1. Create your feature branch (git checkout -b my-new-feature)
1. Commit your changes (git commit -am 'Add some feature')
1. Push to the branch (git push origin my-new-feature)
1. Create a new Pull Request

## Licence

[MIT License](https://github.com/takafumir/javascript-lemmatizer/blob/master/LICENCE.txt)

## Author

[Takafumi Yamano](https://github.com/takafumir)
