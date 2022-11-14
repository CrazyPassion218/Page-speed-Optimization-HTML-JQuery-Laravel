## About Laravel 9 + Tailwind + Alpine JS Multilanguage Landing Page Starter Kit GDPR Comply

version: 1.2
check the working version on [laravel.lots-of-online.work](https://laravel.lots-of-online.work/)

Uses:

-Laravel 9 - Basic Example-app
        
-Mcamara/laravel-localization https://github.com/mcamara/laravel-localization

-Alpine.js  https://github.com/alpinejs/alpine

-TailwindCss https://tailwindcss.com/

-Kitwind UI https://kitwind.io/products/kometa

-Laravel Mix Extract Media Queries https://github.com/elambro/laravel-mix-extract-media-queries

-Laravelium Sitemap package https://github.com/Laravelium/laravel-sitemap

-Spatie / laravel-cookie-consent https://github.com/spatie/laravel-cookie-consent

-Laravel HTML Minifier https://github.com/dipeshsukhia/laravel-html-minify



The main goal is to create a multilingual landing page starter kit with full SEO titles and headings and with Google Pagespeed close to 100.

Made just for me, but anyone can use and modify if needed =)

In this version, I got 80-100 points in desktop version and 90-100 points in mobile with Font-awesome CDN enabled and 100/100 score without fonts. The results may vary due to the server.

## Requirements

PHP 8+. If you do not have PHP 8 and want to use PHP 7 you should remove  "Spatie / laravel-cookie-consent" or downgrade it to lower version. Read discussion on their gitHub.  

## Change Log

Version 1.2
- Added 'laravel-mix-compress'
- Updated NPM deps
- Updated project to Laravel 9
- Added GA4 script to header as an example

Version 1.1
- Added 'laravel-cookie-consent' to comply with GDPR law. 
- Added a script that checks the cookie created by 'laravel-cookie-consent' if user accepts cookies.
- Added components to run scripts in header/body and footer. 
- Added automatic generation of sitemap by 
- Added HTML minifier

Version 1.0
-Basic template done
## Installation for Development

-Download git repo "git clone https://github.com/seosmmbusiness/multilang-laravel-kit.git"

-Run "composer install"

-Run "npm i"

-Run "npm run dev"

-Run "php artisan serve"

## Deployment Laravel 9 Starter Kit on Apache Server

-Download git repo "git clone https://github.com/seosmmbusiness/multilang-laravel-kit.git" to your home directory and open it

-Run "composer install --no-dev"

-Make changes in .env file (APP NAME, URL and etc)

-Run "php artisan key:generate"

-Create a symlink to html directory (it can be puclic_html or  /var/www/html be or the one your apache server uses) from multilang-laravel-kit/public 
In my case "ln -s /home/user/multilang-laravel-kit/public /home/user/public_html"

or

change your Apache server public dir to laravel project's public dir

-Run "php artisan optimize"

-Run "php artisan route:trans:cache"

## Todoo

-Add more SEO meta tags 

-Add AMP 

-Add PWA       // Made few tests so far and got bad results in page load.

-Increase mobile speed with additional fonts

## Additional info

## Css file generate with webpackmix
- webpack.mix.js
In "mix.extractMediaQueries" specify "breakpoints: [640, 768, 1024]" according to used in css;
run "npm run prod" to generate new css files;
add to master.blade preload and links to new scripts.
## Cache routes with languages
- Cache routes
According to Mcamara use "php artisan route:trans:cache" to cache routes. Without it the error is possible!

## Comply with GDPR and run ads

- To comply with GDPR law you need to inform that your website uses cookies and you should not run any scripts before user agree with it. (In best practice you also need to make the visitor to check and choose the scripts to run and cookies to save.)
- To run Javascript after the visitor accepted the cookies you need to put JS in the scriptsToRun.blade.php. Without <scripts> tag.

Basicly my practice: I put tag manager scripts with <script></script> in header-scripts component and middle-scripts component. After that you can check for cookie generated by 'laravel-cookie-consent' in your Tag Manager.

For ads, I run the basic Adsense script in header or footer.
        <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js">
        <script>
        (adsbygoogle=window.adsbygoogle||[]).pauseAdRequests=1;   //Pauses the ads until get the agreement
        (adsbygoogle=window.adsbygoogle||[]).push({google_ad_client: "ca-pub-XXXXXX", enable_page_level_ads: true});
        </script>

And after that in the scriptsToRun write: 

(adsbygoogle=window.adsbygoogle||[]).requestNonPersonalizedAds=0;    //or 1 if you do not want to run personalized ads.
(adsbygoogle=window.adsbygoogle||[]).pauseAdRequests=0;             //Start running ads

So once the visitor accepts with cookies the ads runs.

## Troubleshooting
Feel free to contact me or open an Issue =)


Already solved. Will leave it here for some time.
In case "npm run prod" shows error "TypeError: compiler.plugin is not a function" with "extract-css-media-queries" plugin possibly there is an case with a new webpack plugin system. 

Make sure that the file "src/index.js" in "extract-css-media-queries" in "node_modules" has "compiler.hooks.emit.tapAsync('emit', (compilation, callback) => {" instead of "compiler.plugin('emit', (compilation, callback) => {"

## Contributing

Thank you for considering contributing to the Laravel 8 + Tailwind + Alpine JS Multilanguage Landing Page Starter Kit!

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
            
## Websites built on the template:
Contact me to add your website ;)
            
- [SMM Panel](https://smm.work/en)
- [Options signals](https://options-signals.com/en)

