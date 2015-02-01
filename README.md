# Gracie
## a graceful  mixin-based SCSS grid library

Run `npm run sass` to compile demo. 


TODO:  Implement Push and Pull classes !



    Example usage for generating "sematic" grid elements.

    <div class="wrapper">
      <header class="header">
          <div class="logo"><img src="logo.png"/></div>
          <div class="menu"><nav>...</nav></div>
      </header>
    </div>

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

Gracie requires the use of box-sizing: border-box, which is a best practice these days anyways.

See: http://www.paulirish.com/2012/box-sizing-border-box-ftw/

If you don't have box sizing enable's elsewhere in your SCSS-stack, set `$grid-enable-border-box` to true to enable it.

Gracie is focused on building sematic grid via mixins, but if you wish to generate grid classesala Bootstrap, set $grid-classes to true.
 
Generated class names will follow the following convention

    .col-#{$breakpoint}-#{$span}

    .col-small-6;   This component will span 6 columns from 20ems up
    .col-medium-12; This component will span 12 columns from 48ems up



Example usage for generating non-sematic grid elements.
 
    <div class="container">
        <header class="row">
            <div class="col-medium-4"><img src="logo.png"/></div>
            <div class="col-medium-6"><nav>...</nav></div>
        </header>
    </div>

