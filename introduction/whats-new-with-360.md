# What's New in 3.6.0

This release was all about improvements to the core, localization and internationalization for sites, many bug fixes, UI improvements and updates to our containerization strategy.  Please see below the major areas of improvement and our full release notes.

## New Installer Module

The installer module is now available as a standalone module using the slug `contentbox-installer-module`.  This will improve our container and your container strategy as now you can bring in the installer on demand via CommandBox.

```bash
install contentbox-installer-module
```

## Ability to contribute CSS to CKEditor

Thanks to the Computer Know How guys you can contribute your own CSS files to the CKEditor instance so the content has your theme's look and feel.  Please note, this is mostly usable for theme developers and module developers.

The event is called `cbadmin_ckeditorContentsCss` and it will receive a struct with one key called `contentsCss` which is an array.  You can then append CSS style sheets to that array that CKEditor will showcase.


```js
function cbadmin_ckeditorContentsCss( event, interceptData ){
  // Add css
  interceptData.contentsCss.append( "/path/theme.css" );
}

## Site Localization Updates

Thanks to the Computer Know How guys, this release sports many i18n improvements.

### Changing Site Locales

A ContentBox application depends on the ColdBox i18n module which gives you the ability to serve any content in any language, use resource bundles and use the resource utilities.  However, we have now exposed the ability natively for users to change locales via the UI module using our URL of: `http://site.com/__changelang/en_US`.  The route expects an ISO valid language code in the format of `code_variant`.  

> **Note** By default, visitor locale's are stored in the `cookie` scope. You can change this via the `config/Coldbox.cfc` configuration CFC.


### Generating Locale Links

The `CBHelper` object can now produce these links for you in your layouts, themes and views by leveraging the following method:

```js
/**
 * Link to the __changeLang route, this is where the fwLocale is changed
 * @lang The iso language code
 */
function linkLanguageChange( string lang = "en_US" ) {
	return getRequestContext().buildLink( '__changeLang/' & arguments.lang );
}
```

### Locale Content Caching

All caching strategies have now been updated to allow for locale to determine its key.  This way, every visitor's language will be cacheable and performant.