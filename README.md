README
======

HtmlkickStartBundle
-------------------

HtmlkickStartBundle allows you to quickly integrate the Html KickStart framework of Joshua Gatcke in a symfony2 project.
To know more about Html KickStart, please visit http://www.99lime.com


Installation
------------

First add the folowing lines to your deps file:


	[HtmlKickstartBundle]
		git=http://github.com/floarc/HtmlKickstartBundle.git
		target=/bundles/NinetyNineLime/HtmlKickstartBundle
		
	[HtmlKickstart]
		git=https://github.com/joshuagatcke/HTML-KickStart.git
		target=/bundles/NinetyNineLime/HtmlKickstartBundle/Resources/public		

Be sure that HtmlKickstartBundle is declared BEFORE HtmlKickstart in your deps file.
		
Then in the console go to the root of your symfony2 preject diretory

and launch the command:


    ./bin/vendors install --reinstall


IMPORTANT NOTE: 
Launching the usual command ./bin/vendors install is not enough. 
You MUST add the argument  --reinstall


Then edit your app/AppKernel.php file in the function registerBundles in the array $bundles add the folowing line :

    new NinetyNineLime\HtmlKickstartBundle\NinetyNineLimeHtmlKickstartBundle(),


Then edit you app/autoload.php and add the folowing Namespace below "$loader->registerNamespaces(array(" and after previous namespace declarations:

    'NinetyNineLime'   => __DIR__.'/../vendor/bundles',


Go back to the console and launch:

    php app/console assets:install web

And your done!


99Lime Html KickStart is now available as a web ressource.


How To use in a layout
----------------------


So you can use the folowing lines to start your html layout:

``` php
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
```

Macros
------

This bundle ship with a set of macros (more will come) available in Resources/views/macro, you can import and use it
in your templates if you need to. You can find more information about twig macros here: http://twig.sensiolabs.org/doc/tags/macro.html
