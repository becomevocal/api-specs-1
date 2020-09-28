# Available APIs

<div class="otp" id="no-index">

### On this page
- [Management APIs](#management-apis)
- [Storefront APIs](#storefront-apis)
- [Payment Processing API](#payment-processing-api)
- [Provider APIs](#provider-apis)

</div>

## Management APIs

### V2 REST API

BigCommerce's **V2 REST API** exposes many endpoints developers can use to programmatically interact with store resources (including webhooks). Some **V2 API** resources are not yet exposed in the **V3 API**; however, for resources that are accessible via both APIs, the **V3 API** is recommended, as it contains performance optimizations as well as a number of [other improvements](#v3-rest-api).

**Server**: `api.bigcommerce.com/stores/{store_hash}/v2`

### V3 REST API

Like the **V2 API**, BigCommerce's **V3 REST API** exposes many endpoints developers can use to programmatically interact with store resources (including [server-to-server carts](https://developer.bigcommerce.com/api-reference/cart-checkout/server-server-cart-api) and [checkouts](https://developer.bigcommerce.com/api-reference/cart-checkout/storefront-checkout-api) for using BigCommerce headlessly). Interactions with the **V3** API are very similar to that of the **V2** API; however, the **V3** API introduces a number of improvements:
* Most tasks can be performed with fewer API calls (for example, a product with variants and custom fields can be created in a single request)
* Each **V3** resource includes a `meta` object, simplifying pagination
* **V3** Brands, Categories, Products, and Product Variants expose a [metafields](https://developer.bigcommerce.com/api-reference/catalog/catalog-api/product-metafields/createproductmetafield) resource for use by developers to store custom data.
* **V3** API is optimized for performance (in general, data can be sent, received, and processed faster via **V3**, relative to **V2**).

**Server**: `api.bigcommerce.com/stores/{store_hash}/v3`

**Additional Information:** [About our APIs](https://developer.bigcommerce.com/api-docs/getting-started/about-our-api) | [Authentication](https://developer.bigcommerce.com/api-docs/getting-started/authentication) | [API Status Codes](https://developer.bigcommerce.com/api-docs/getting-started/api-status-codes)

## Storefront APIs

### Storefront REST API

BigCommerce's **Storefront API REST** is a client API that exposes storefront data to stencil themes. The Storefront API can be used to manage a shopper's cart and checkout and fetch order data via client-side JavaScript.

**Server**: `{store_domain}/api/storefront`

**Additional Information:** [Storefront Cart and Checkout Overview](https://developer.bigcommerce.com/api-docs/cart-and-checkout/cart-and-checkout-overview) | [Working with Storefront APIs](https://developer.bigcommerce.com/api-docs/cart-and-checkout/working-sf-apis) |

### Storefront GraphQL API

BigCommerce’s **GraphQL Storefront API** makes it possible to query storefront data from within a Stencil theme or remote site. This means information previously only available on the back-end via Stencil’s template logic can now be accessed via front-end JavaScript. Additionally, by leveraging the power of GraphQL, data for multiple resources can be returned from a single API call, which simplifies integration and increases performance so that developers can focus on building delightful shopper experiences.

**Server**: `{store_domain}/graphql`

| Reference Documentation |
|-------------------------|
| [GraphQL PlayGround](https://developer.bigcommerce.com/graphql-playground)  |
| [GraphQL Explorer](https://developer.bigcommerce.com/graphql-explorer)    |

**Additional Information:** [GraphQL Storefront API Overview](https://developer.bigcommerce.com/api-docs/storefront/graphql/graphql-storefront-api-overview)

### Add to cart URLs

Query string parameters can be appended to BigCommerce product and `/cart.php` URLs in order to pre-select an SKU or add a product to cart. These parameters make it possible to build custom add to cart links and forms for use on BigCommerce storefronts and remote sites (such as WordPress, blog posts, and social media).

**Server**: `{store_domain}`

**Additional Information:** [Add to Cart URLs Overview](https://developer.bigcommerce.com/api-docs/cart-and-checkout/add-to-cart-url)

### Customer Login API

The **Customer Login API** enables single sign-on (SSO). It allows apps to programmatically log in a storefront customer via `/login/token/{token}`, where`{token}` is a JSON Web Token (`JWT`) containing the parameters for the customer login request, signed by the application’s `OAuth` **client secret**.

**Server**: `{store_domain}`

**Additional Information**: [Customers & Subscribers Overview](https://developer.bigcommerce.com/api-docs/customers/customers-subscribers-overview)

### Current Customer API

Apps that interact dynamically with a BigCommerce storefront and convey information specific to a particular logged-in customer must confirm the customer's identity within the insecure environment of the customer's browser.

To address this need, BigCommerce provides a Current Customer endpoint accessibly via client-side JavaScript. This endpoint returns a `JWT` with identifying details about the customer. The information is signed with an `OAuth` **client secret**.

**Server**: `{store_domain}`

**Additional Information**: [Customers & Subscribers Overview](https://developer.bigcommerce.com/api-docs/customers/customers-subscribers-overview)

## Payment Processing API

Using the Payment Processing API, developers can programmatically process payments through a BigCommerce store's payment gateway.

**Server**: `payments.bigcommerce.com/stores/{store_hash}`

**Additional Information:** [Payment Processing API Overview](https://developer.bigcommerce.com/api-docs/payments/payments-api-overview)


## Provider APIs

Provider API references describe endpoints, responses, and requests that can be implemented by partners and consumed by BigCommerce for the purpose of creating custom integrations (ex: custom shipping carrier rates via `/rates`).

**Server**: `{providers_server}`

**Additional Information:** [Shipping Provider API Overview](https://developer.bigcommerce.com/api-docs/store-management/shipping/shipping-provider-api)