<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Gamma Scaled Lanczos Sum

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Calculate a scaled Lanczos sum for the approximation of the [gamma function][gamma-function].

<section class="intro">

The [Lanczos approximation][lanczos-approximation] for the [gamma function][gamma-function] can be written in partial fraction form as follows:

<!-- <equation class="equation" label="eq:lanczos_approximation" align="center" raw="\Gamma ( n ) = \frac{(n+g-0.5)^{n-0.5}}{e^{n+g-0.5}} L_g(n)" alt="Lanczos approximation for gamma function."> -->

```math
\Gamma ( n ) = \frac{(n+g-0.5)^{n-0.5}}{e^{n+g-0.5}} L_g(n)
```

<!-- <div class="equation" align="center" data-raw-text="\Gamma ( n ) = \frac{(n+g-0.5)^{n-0.5}}{e^{n+g-0.5}} L_g(n)" data-equation="eq:lanczos_approximation">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@bb29798906e119fcb2af99e94b60407a270c9b32/lib/node_modules/@stdlib/math/base/special/gamma-lanczos-sum-expg-scaled/docs/img/equation_lanczos_approximation.svg" alt="Lanczos approximation for gamma function.">
    <br>
</div> -->

<!-- </equation> -->

where `g` is an [arbitrary constant][@stdlib/constants/float64/gamma-lanczos-g] and `L_g(n)` is the Lanczos sum. The scaled Lanczos sum is given by 

<!-- <equation class="equation" label="eq:scaled_lanczos_sum" align="center" raw="L_g(n) \cdot \exp(-g)" alt="Scaled Lanczos sum."> -->

```math
L_g(n) \cdot \exp(-g)
```

<!-- <div class="equation" align="center" data-raw-text="L_g(n) \cdot \exp(-g)" data-equation="eq:scaled_lanczos_sum">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@bb29798906e119fcb2af99e94b60407a270c9b32/lib/node_modules/@stdlib/math/base/special/gamma-lanczos-sum-expg-scaled/docs/img/equation_scaled_lanczos_sum.svg" alt="Scaled Lanczos sum.">
    <br>
</div> -->

<!-- </equation> -->

</section>

<!-- /.intro -->



<section class="usage">

## Usage

To use in Observable,

```javascript
gammaLanczosSumExpGScaled = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var gammaLanczosSumExpGScaled = require( 'path/to/vendor/umd/math-base-special-gamma-lanczos-sum-expg-scaled/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.gammaLanczosSumExpGScaled;
})();
</script>
```

#### gammaLanczosSumExpGScaled( x )

Calculates the Lanczos sum for the approximation of the [gamma function][gamma-function] (scaled by `exp(-g)`, where `g = 10.900511`).

```javascript
var v = gammaLanczosSumExpGScaled( 4.0 );
// returns ~0.018

v = gammaLanczosSumExpGScaled( -1.5 );
// returns ~25.337

v = gammaLanczosSumExpGScaled( -0.5 );
// returns ~-12.911

v = gammaLanczosSumExpGScaled( 0.5 );
// returns ~1.772

v = gammaLanczosSumExpGScaled( 0.0 );
// returns Infinity

v = gammaLanczosSumExpGScaled( NaN );
// returns NaN
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-linspace@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled@umd/browser.js"></script>
<script type="text/javascript">
(function () {

var x = linspace( -10.0, 10.0, 100 );

var i;
for ( i = 0; i < x.length; i++ ) {
    console.log( 'x: %d, f(x): %d', x[ i ], gammaLanczosSumExpGScaled( x[ i ] ) );
}

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/math-base/special/gamma`][@stdlib/math/base/special/gamma]</span><span class="delimiter">: </span><span class="description">gamma function.</span>
-   <span class="package-name">[`@stdlib/math-base/special/gamma-lanczos-sum`][@stdlib/math/base/special/gamma-lanczos-sum]</span><span class="delimiter">: </span><span class="description">calculate the Lanczos sum for the approximation of the gamma function.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## Copyright

Copyright &copy; 2016-2024. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/math-base-special-gamma-lanczos-sum-expg-scaled.svg
[npm-url]: https://npmjs.org/package/@stdlib/math-base-special-gamma-lanczos-sum-expg-scaled

[test-image]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/actions/workflows/test.yml/badge.svg?branch=v0.2.0
[test-url]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/actions/workflows/test.yml?query=branch:v0.2.0

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled?branch=v0.2.0

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled.svg
[dependencies-url]: https://david-dm.org/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/tree/deno
[deno-readme]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/tree/umd
[umd-readme]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/tree/esm
[esm-readme]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum-expg-scaled/blob/main/branches.md

[@stdlib/constants/float64/gamma-lanczos-g]: https://github.com/stdlib-js/constants-float64-gamma-lanczos-g/tree/umd

[gamma-function]: https://en.wikipedia.org/wiki/Gamma_function

[lanczos-approximation]: https://en.wikipedia.org/wiki/Lanczos_approximation

<!-- <related-links> -->

[@stdlib/math/base/special/gamma]: https://github.com/stdlib-js/math-base-special-gamma/tree/umd

[@stdlib/math/base/special/gamma-lanczos-sum]: https://github.com/stdlib-js/math-base-special-gamma-lanczos-sum/tree/umd

<!-- </related-links> -->

</section>

<!-- /.links -->
