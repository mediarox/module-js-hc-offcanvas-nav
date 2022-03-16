# Magento 2 module for hc-offcanvas-nav (6.1.4)

**This repo is just an integration of original js-library including css into Magento 2.**

> JavaScript library for creating off-canvas multi-level navigations, using ARIA. Dependency free, but also works as a jQuery plugin.

See original repository for more information: https://github.com/somewebmedia/hc-offcanvas-nav

### Installation

```bash
cd <magento_root>
composer require mediarox/module-js-hc-offcanvas-nav
bin/magento setup:upgrade
```
### Usage example

```php
?>
<script>
    require([
        'jquery',
        'hcOffcanvasNav'
    ], function ($, hcOffcanvasNav) {
        // create global instance. info: the call as jQuery plugin ($(selector).hcOffcanvasNav) does not work reliably.
        window.topMenuNavigation = new hcOffcanvasNav('nav.navigation', {
            disableAt: 768,
            labelBack: '<?= $escaper->escapeHtml(__('Back')) ?>',
            width: '100%',
            levelTitles: true,
            levelTitleAsBack: true
        });
        // handle magento mobile nav trigger click. (the "customToggle" option causes collisions in the design.)   
        $('[data-action="toggle-nav"]').on('click', function(event) {
            event.preventDefault();
            window.topMenuNavigation.open();
        });
    });
</script>
```