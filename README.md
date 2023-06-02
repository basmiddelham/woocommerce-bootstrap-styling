# Woocommerce Bootstrap styling

Replacement for WooCommerce CSS for use in your Bootstrap project.

Check out the [demo](https://sagestarter.middelham.nl/shop) of this project.

Add this this your `functions.php`to disable default stylesheets and add WooCommerce support:

```
if (class_exists('woocommerce')) {

  // Disable the default WooCommerce stylesheets.
  add_filter('woocommerce_enqueue_styles', '__return_empty_array');

  // Add Woocommerce support and enable Woocoommerce gallery.
  add_action('after_setup_theme', function () {
    add_theme_support('woocommerce');
    add_theme_support('wc-product-gallery-zoom');
    add_theme_support('wc-product-gallery-lightbox');
    add_theme_support('wc-product-gallery-slider');
  });
}
```

## Header cart

To use the ajax powered mini-cart in your header add [this](https://github.com/MoshCat/woocommerce-header-cart/blob/master/woocommerce-header-cart.php) to your theme.

## Widgets

To use the WooCoomerce widgets you would also needs this basic [WordPress widget styling](https://gist.github.com/MoshCat/d2822941189762d0a03718cc192b0925).

## Change breadcrumb to Bootstrap defaults

Use this filter to change the WooCommerce breadcrumb to use Bootstrap classes.

```
/**
 * Change breadcrumb to Bootstrap defaults
 */
add_filter('woocommerce_breadcrumb_defaults', function () {
    return array(
        'delimiter'   => '',
        'wrap_before' => '<nav class="woocommerce-breadcrumb" aria-label="breadcrumb"><ol class="breadcrumb">',
        'wrap_after'  => '</ol></nav>',
        'before'      => '<li class="breadcrumb-item">',
        'after'       => '</li>',
        'home'        => __('Home', 'breadcrumb', 'sage'),
    );
});
```
