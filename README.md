# jQuery Character Counter Plugin

This plugin provides the ability to associate a character counter with a text area.

## Install

Install either via Bower:

    bower install jquery-charactercounter-plugin

Or by downloading the `jquery.charactercounter.js` file directly and placing in your chosen location.

## Usage

After including the plugin, use it by first adding some data attributes to your textarea and adding an element which will serve as the container for your counter. Your counter element can be anything you like and styled however you like, with other classes and so on. The content will be updated using jQuery's `text()` method.

    <textarea id="example1"
              data-max-chars="200"
              data-counter-element="#example1-counter"></textarea>
    <span id="example1-counter"></span>

Then just initialise the plugin, passing it any appropriate options if you wish to customise the behaviour beyond the defaults. See below for all available options.

    $('#example1').characterCounter();

    $('#example2').characterCounter({
        postCountMessage: "characters left",
        postCountMessageSingular: "character left",
        zeroRemainingMessage: "No characters left",
        overrunPreCountMessage: "Please remove",
        overrunPostCountMessage: "characters",
        overrunPostCountMessageSingular: "character",
        positiveOverruns: true
    });

### Options

These options can be specified to customise the behaviour of the character counter. The default values are also given below.

| Option | Description | Default
| ------ | ----------- | -------
| `elementClass` | Class assigned to the character count element. | `"me-character-counter"`
| `validClass` | Class applied to the character counter (in addition to the `elementClass` value) when it is in a valid state. | `"me-character-counter_valid"`
| `invalidClass` | Class applied to the character counter (in addition to the `elementClass` value) when it is in an invalid state. | `"me-character-counter_invalid"`
| `maxChars` | Maximum allowed characters before being considered invalid. | `Infinity`
| `minChars` | Minimum number of characters allowed before being considered invalid. | `0` 
| `counterElement` | Element to use for the character counter. If `null`, one is created. | `null`
| `positiveOverruns` | Whether or not overruns should be counted positive rather than negative. | `false`
| `newLinesAsTwoChars` | Whether newlines (`\r`, `\n` and `\r\n`) always be counted as two characters. | `true`
| `postCountMessage` | String shown after character count (e.g. "characters left"). | `null`
| `preCountMessage` | String shown before character count (e.g. "you have"). | `null`
| `postCountMessageSingular` | Same as `postCountMessage` but for the singular case. If not provided, `postCountMessage` will be used. | `null`
| `preCountMessageSingular` | Same as `preCountMessage` but for the singular case. If not provided, `preCountMessage` will be used. | `null`
| `zeroRemainingMessage` | Message shown when 0 characters remain (e.g. "No characters left"). If not set, zero is treated just like any other number. | `null`
| `overrunPostCountMessage` | Same as `postCountMessage` but used once the user has ran over the allocated character count. | `null`
| `overrunPreCountMessage` | Same as `preCountMessage` but used once the user has ran over the allocated character count. | `null`
| `overrunPostCountMessageSingular` | Same as `overrunPostCountMessage` but for the singular case. If not provided, `overrunPostCountMessage` will be used. | `null`
| `overrunPreCountMessageSingular` | Same as `overrunPreCountMessage` but for the singular case. If not provided, `overrunPreCountMessage` will be used. | `null`
