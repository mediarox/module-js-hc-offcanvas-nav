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
        $('#mobile-nav').hcOffcanvasNav({
            disableAt: 768,
            customToggle: $('.toggle'),
            navTitle: '<?= $escaper->escapeHtml(__('Back')) ?>',
            levelTitles: true,
            levelTitleAsBack: true
        });
    });
</script>
```