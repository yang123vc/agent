Laravel 4 User Agent
====================

A user agent class for Laravel 4, based on [Mobile Detect](https://github.com/serbanghita/Mobile-Detect) with extended functionality.

Installation
------------

Add the package to your composer.json and run `composer update`.

	{
	    "require": {
	        "jenssegers/agent": "*"
	    }
	}

And add the Agent alias to `app/config/app.php`:

	'Agent'            => 'Jenssegers\Agent\Facades\Agent',

Basic Usage
-----------

All of the original [Mobile Detect](https://github.com/serbanghita/Mobile-Detect) is still available, check out more examples over at https://github.com/serbanghita/Mobile-Detect/wiki/Code-examples

### Agent::is()

Check for a certain property in the user agent.

	Agent::is('Windows');
	Agent::is('Firefox');
	Agent::is('iPhone');
	Agent::is('OS X');

### Magic is-method

Magic method that does the same as the previous `is()` method:

	Agent::isAndroidOS();
	Agent::isNexus();
	Agent::isSafari();

### Mobile detection

Check for mobile device:

	Agent::isMobile();
	Agent::isTablet();

### Match user agent

Search the user agent with a regular expression:

	Agent::match('regexp');

Additional Functionality
------------------------

Since the original library was inspired on CodeIgniter, I decided to add some additional functionality:

### Agent::languages()

Get the browser's accept languages. Example:

	['nl-nl', 'nl', 'en-us', 'en']

### Agent::device()

Get the device name, if mobile. (iPhone, Nexus, AsusTablet, ...)

### Agent::platform()

Get the operating system. (Ubuntu, Windows, OS X, ...)

### Agent::browser()

Get the browser name. (Chrome, IE, Safari, Firefox, ...)

### Agent::isRobot()

Check if the user is a robot.
