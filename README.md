README
======



Installation
------------

First add the folowing lines to your deps file:

[HtmlKickstartBundle]
    git=http://github.com/floarc/HtmlKickstartBundle.git
    target=/bundles/NinetyNineLime/HtmlKickstartBundle
    
Then in the console go to the root of your symfony2 preject diretory

and lauch the usual command:
./bin/vendors install

Then:    
cd ./vendor/bundles/NinetyNineLime/HtmlKickstartBundle
git submodule init
git submodule update


Then edit your app/AppKernel.php file in the function registerBundles in the array $bundles add the folowing line :

new NinetyNineLime\HtmlKickstartBundle\NinetyNineLimeHtmlKickstartBundle(),


Then edit you app/autoload.php and add the folowing Namespace below "$loader->registerNamespaces(array(" and after previous namespace declarations:

'NinetyNineLime'   => __DIR__.'/../vendor/bundles',


Go back to the console adn launch:

php app/console assets:install web

And your done!


99Lime HtmlkickStart is now available as a web ressource.


How To use in a layout
----------------------


So you can use the folowing lines to start your html layout:
'''
<!DOCTYPE html>
<html><head>
<meta charset="UTF-8">
<meta name="description" content="" />
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.4/jquery.min.js"></script>
<!--[if lt IE 9]><script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script><![endif]-->
<script type="text/javascript" src="/bundles/ninetyninelimehtmlkickstart/js/prettify.js"></script>                                   <!-- PRETTIFY -->
<script type="text/javascript" src="/bundles/ninetyninelimehtmlkickstart/js/kickstart.js"></script>                                  <!-- KICKSTART -->
<link rel="stylesheet" type="text/css" href="/bundles/ninetyninelimehtmlkickstart/css/kickstart.css" media="all" />                  <!-- KICKSTART -->
<link rel="stylesheet" type="text/css" href="/bundles/ninetyninelimehtmlkickstart/style.css" media="all" />                          <!-- CUSTOM STYLES -->
</head><body>
...
..
.
..
...
</body>
</html>
'''