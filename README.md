# VUE

### Conditional Rendering

```js
<div id="app">
    <h1>{{ product }} Products</h1>
    <p v-if='inStock'>in stock</p>
    <p v-else-if='inventory > 0 && inventory <= 10'>Almost sold out</p>
    <p v-else>out of stock</p>
</div>
```

### List Rendering

1.
```js
<ul>
    <li v-for="detail in details">{{ detail }}</li>
</ul>


javascript:

var app = new Vue({
    data: {
        details: ['first', 'second', 'third']
    }
})
```

2.
```js
<ul>
    <li v-for="variant in variants" :key="variant.variantId">
        {{ variant.variantColor }}
    </li>
</ul>

javascript:

var app = new Vue({
    data: {
        variants: [
            {
                variantColor: 'red',
                variantId: 123
            },
            {
                variantColor: 'blue',
                variantId: 456
            }
        ]
    }
})
```

### Event Handling

1.
```js
<h3>{{ cart }}</h3>
<button v-on:click='cart += 1'>addCart</button>

javscript: 

var app = new Vue({
    el: '#app',
    data: {
        cart: 0
    }
})
```

2.
```js
<h1>{{ cart }}</h1>
<button v-on:click='addToCart'></button>

var app = new Vue({
    el: '#app',
    data: {
        cart: 0
    },
    methods: {
        addToCart() {
            this.cart += 1
        }
    }
})
```

* `hover` is equal to `@mouseover`

other events:

`@submit`, `@keyup.enter`  .enter is `modifier`


### inlineStyling

```js
<div :style='{ backgroundColor: 'red' }'>backgroundColor</div>
<div :style='{ backgroundColor: variant.variantColor }'>backgroundColor</div>
```

### disableAttribute

to make a button `disabled` according to a specific condition

```js
var app = new Vue({
    el: '#app',
    data: {
        inStock: true,
        cart: 0
    },
    methods: {
        addToCart() {
            this.cart += 1
        }
    }
})

<button v-on:click='addToCart' :disabled='!inStock'>addToCart</button>
```

### class Bindings

1.
```js
<div :class="{ active: activeClass, 'text-danger': errorClass }"></div>

data: {
    activeClass: true,
    errorClass: false
}

So 

<div class="active"></div>
```

2. Objects
```js
<div :class="classObject"></div>

data: {
    classObject: {
        active: true,
        'text-danger': false
    }
}

So

<div class="active"></div>
```

3. Array
```js
<div :class="[activeClass, errorClass]"></div>

data: {
    activeClass: 'active',
    errorClass: 'text-danger'
}

So

<div class='active text-danger'></div>
```

4. Conditionals
```js
<div :class="[isActive ? activeClass : '']"></div>

data: {
    isActive: true,
    activeClass: 'active'
}
```
