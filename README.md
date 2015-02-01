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

