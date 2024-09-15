# TermsFeed Free Cookie Consent, version 4.1

Free Cookie Consent is a free cookies management solution by [TermsFeed](https://www.termsfeed.com) that you can integrate on your website that helps you comply with the EU Cookies Directive and GDPR.

**Important!** This is version 4.1, the latest version is [Cookie Consent 4.2](https://github.com/termsfeed/termsfeed-cookie-consent-4-2)

# Installation

## Hosted by TermsFeed

1. Load the Cookie Consent from TermsFeed domain.

        <script type="text/javascript" src="//www.termsfeed.com/public/cookie-consent/4.1.0/cookie-consent.js" charset="UTF-8"></script>

2. Append the config code.
3. Add the code after the `<body>` tag or before the `</body>` tag on your web pages. Example:

        <script type="text/javascript" src="//www.termsfeed.com/public/cookie-consent/4.1.0/cookie-consent.js"></script>
        <script type="text/javascript">
            document.addEventListener('DOMContentLoaded', function () {
                cookieconsent.run({
                    "notice_banner_type": "headline",
                    "website_privacy_policy_url": "http://www.termsfeed.com/",
                    "consent_type": "express",
                    "palette": "light",
                    "website_name": "TermsFeed Cookie Consent",
                    "language": "en",
                    "open_preferences_center_selector": "#changePreferences",
                    "preferences_center_close_button_hide": false,
                    "page_load_consent_levels": ["strictly-necessary"]
                });
            });
        </script>

## Self-host

1. Copy the `cookie-consent.js` from `dist/` folder.
2. Append the config code.
3. Add the code after the `<body>` tag or before the `</body>` tag on your web pages. Example:

        <script type="text/javascript" src="cookie-consent.js"></script>
        <script type="text/javascript">
            document.addEventListener('DOMContentLoaded', function () {
                cookieconsent.run({
                    "notice_banner_type": "headline",
                    "website_privacy_policy_url": "http://www.termsfeed.com/",
                    "consent_type": "express",
                    "palette": "light",
                    "website_name": "TermsFeed Cookie Consent",
                    "language": "en",
                    "open_preferences_center_selector": "#changePreferences",
                    "preferences_center_close_button_hide": false,
                    "page_load_consent_levels": ["strictly-necessary"]
                });
            });
        </script>

# Usage

In order for the Cookie Consent tool to run correctly, you need to "tag" your JS scripts:

1. Change `type="text/javascript"` to `type="text/plain"`. If `type="text/javascript"` is not available, add `type="text/plain"`.
2. On the same `<script>`, add in the corresponding cookie level: `data-cookie-consent="functionality"`.

Here's an example:

    <!-- Login Cookies -->
    <script type="text/plain" data-cookie-consent="strictly-necessary" src="/js/login-session.js"></script>

    <!-- Google Analytics -->
    <script type="text/plain" data-cookie-consent="tracking">
    (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
    (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
    })(window,document,'script','//www.google-analytics.com/analytics.js','ga');
    ga('create', GOOGLE_PROPERTY_ID_GOES_HERE, 'auto');
    ga('send', 'pageview');
    </script>

# Example

The below example includes the install + config code, the button to open Preferences Center and an example of JS script tagged.

    <!-- Cookie Consent by TermsFeed https://www.TermsFeed.com -->
     <script type="text/javascript" src="//www.termsfeed.com/public/cookie-consent/4.1.0/cookie-consent.js" charset="UTF-8"></script>
    <script type="text/javascript" charset="UTF-8">
        document.addEventListener('DOMContentLoaded', function () {
            cookieconsent.run({
                    "notice_banner_type": "headline",
                    "website_privacy_policy_url": "http://www.termsfeed.com/",
                    "consent_type": "express",
                    "palette": "light",
                    "website_name": "TermsFeed Cookie Consent",
                    "language": "en",
                    "open_preferences_center_selector": "#changePreferences",
                    "preferences_center_close_button_hide": false,
                    "page_load_consent_levels": ["strictly-necessary"]
            });
        });
    </script>
    <noscript>Free cookie consent management tool by <a href="https://www.termsfeed.com/">TermsFeed</a></noscript>
    <!-- End Cookie Consent by TermsFeed https://www.TermsFeed.com -->

    <!-- Below is the link that users can use to open Preferences Center to change their preferences. Do not modify the ID parameter. Place it where appropriate, style it as needed. -->
    <button id="changePreferences">Change preferences</button>

    <!-- Google Analytics -->
    <script type="text/plain" data-cookie-consent="tracking">
    (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
    (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
    })(window,document,'script','//www.google-analytics.com/analytics.js','ga');
    ga('create', GOOGLE_PROPERTY_ID_GOES_HERE, 'auto');
    ga('send', 'pageview');
    </script>

# Credits Link

The Credits Link must be kept in the HTML source code (see Example above) and inside the Preferences Center.
    
# Design

You can apply your own style for the Cookie Consent by writing your own CSS to overwrite the CSS of Cookie Consent.

Use Developer Tools > Inspect Element to identify the element you want to customize and style differently. Then write your own CSS rules to overwrite the style of the element. For example, if you'd like to make the title of the notice banner red then:

    .termsfeed-com---nb .cc-nb-title {
      color: red !important;
    }

# Methods

The following methods are available for the Cookie Consent:

| Name | Description |
|------|-------------|
| `cookieconsent.run();` | The `run()` method initiates the Cookie Consent. It accepts the configuration options (see below). |

# Configuration Options

The following configurations are available for the Cookie Consent that can be used with the `cookieconsent.run()` method:

| Name | Type | Default | Values | Description |
|------|------|---------|--------|-------------|
| `consent_type` | String | `express` | `express`, `implied` | Type of consent to apply. `implied` will automatically load all tagged JS scripts on page load without waiting for consent. `express` will not load any tagged JS scripts (except strictly necessary) until the user clicks "I Agree". |
| `notice_banner_type` | String | `headline` | `simple`, `headline`, `interstitial`, `standalone` | Type of notice banner design to apply. |
| `palette` | String | `light` | `light`, `dark` | Color palette to apply. |
| `language` | String | `en` | See `i18n/` folder | Language for the text inside the notice banner and Preferences Center. |
| `open_preferences_center_selector` | String | `#changePreferences` | | The ID of the button/link to open the Preferences Center. |
| `website_name` | String | | | The website name to appear in Preferences Center. |
| `website_privacy_policy_url` | String | | | Sets the URL to the Cookies Policy. It appears in the Preferences Center > More Information tab. |
| `website_impressum_url` | String | | | Sets the URL to the Impressum. It appears in the Preferences Center > More Information tab. |
| `notice_banner_insert_legal_urls` | Boolean | `false` | `true`, `false` | Shows the URLs to the Privacy Policy and Impressum in notice banner text (1st layer) |
| `notice_banner_append` |  String | `afterbegin` | `afterbegin`, `beforeend` | Controls where the Cookie Consent injection code is added (afterbegin or beforeend). |
| `preferences_center_close_button_hide` |  Boolean | `false` | `true`, `false` | Shows or hides the "Close" / "X" button in Preferences Center. |
| `page_load_consent_levels` |  Array |  | `["strictly-necessary", "functionality", "tracking", "targeting"]` | Determines the categories of tagged scripts to loaded on page load. The `implied` consent mode should contain all categories while the `express` consent mode should contain only the `strictly-necessary`. |
| `page_refresh_confirmation_buttons` |  Boolean | `false` | `true`, `false` | Refreshes the page upon user's action (i.e. clicking "I Agree" or "I Decline"). |
| `user_consent_token` |  String |  |  | Store your own user consent token (to be used for consent log functionality). |
| `cookie_domain` |  String |  |  | Sets the domain in the stored cookies (to be used for sub-domains). |
| `cookie_secure` |  Boolean | `false` | `true`, `false` | Sets the secure flag for the stored cookies. |
| `demo` |  Boolean | `false` | `true`, `false` | Demo mode will not save any cookies. |
| `debug` |  Boolean | `false` | `true`, `false` | Debug mode will output Console message. |

# Disclaimer

Legal information is not legal advice, [read the disclaimer](https://www.termsfeed.com/legal/disclaimer/).

The provided tool is informational purposes only and do not constitute legal advice.

The information provided here is not legal advice, does not constitute a lawyer referral service, and no attorney-client or confidential relationship is or will be formed by use of the tool.

# License

Shield: [![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
