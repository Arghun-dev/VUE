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
        addToCart: function() {
            this.cart += 1
        }
    }
})
```
