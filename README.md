# woocommerce-bootstrap-styling
Replacement for Woocommerce CSS for use in your Bootstrap project.

Check out the [demo](https://middelham.nl/sagestarter) of this project.

Use:

```
if (class_exists('woocommerce')) {
  // Disable the default WooCommerce stylesheet.
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
