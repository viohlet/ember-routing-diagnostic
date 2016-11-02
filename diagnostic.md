# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    In the router, we let our Ember app know about the other paths we created for the app, and nesting of such apps if any. In the new directories, we have a template (where we can write html and link-to other view states) and the route. The route.js files will contain an array of objects. Basically, our data hook or model.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}} This is the appropiate link :) {{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    Diff 1:
    The first one is nesting a 'product' route inside a 'products' one, and the second is solely a 'product' route. No nesting.
    Diff 2:
    We are giving the route a path to be applied in the url. In the first one, the product id goes immediately after and in the second one, it goes through the 'products' view state first and then we can see the product id. It is all about view states and the dev decision on how to display it.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```route.js
    model: function(params) {
      return [
        {
          id: 123
        }
      ]
    }
    ```

    ```js
    {{#link-to '/movies/123'}} ... {{/link-to}}
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    {{#each model as |whatever|}} ... {{/each}}
    ```
