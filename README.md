# Gracie

Gracie is a graceful [SCSS](http://sass-lang.com/) library focused on building sematic grids via [mixins](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#mixins).

Run `npm run sass` to compile demo. 

TODO: Implement `push` and `pull` classes!

## Semantic grid classes

Example usage for generating "sematic" grid elements.

HTML:

    <div class="wrapper">
        <header class="header">
          <div class="logo"><img src="logo.png"/></div>
          <div class="menu"><nav>...</nav></div>
        </header>
    </div>

SCSS:

    .wrapper { @include make-container; }

    .header {
      @include make-row;

      .logo { @include make-columns(12); }
      .menu { @include make-columns(12); } 

      @include respond-to(medium) {
        .logo { @include make-columns(4); }
        .menu { @include make-columns(6); }
      }

    }

Gracie requires the use of `box-sizing: border-box`, which is a [best practice](http://www.paulirish.com/2012/box-sizing-border-box-ftw/) these days anyways.

If you don't have `box-sizing` enabled elsewhere in your SCSS stack, set `$grid-enable-border-box` to true to enable it.

## Non-semantic grid classes

If you wish to generate grid classes à la [Bootstrap](http://getbootstrap.com/css/#grid), set `$grid-classes` to true.

Example usage for generating non-sematic grid elements.

HTML:

    <div class="container">
        <header class="row">
            <div class="col-medium-4"><img src="logo.png"/></div>
            <div class="col-medium-6"><nav>...</nav></div>
        </header>
    </div>

SCSS:

    .col-#{$breakpoint}-#{$span}

    .col-small-6;   // This component will span 6 columns from 20ems up
    .col-medium-12; // This component will span 12 columns from 48ems up
