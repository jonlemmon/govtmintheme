#How to use

**Copy the theme files**

Place these files into a folder in the theme directory (`your-site/themes/govtmin/`).

**Change your theme setting**

Go into a config file (e.g. `your-site/_config/config.yml`) and alter the `SSViewer.theme` setting to `govtmin`.

**Change Page.php**

Add the following to the `Page_Controller` within `Page.php`

````
init() {

		// theme path
		$themePath = 'themes/' . Config::inst()->get('SSViewer', 'theme');
		
		// js
		Requirements::javascript($themePath . '/thirdparty/jquery-2.1.4.min.js');
		Requirements::javascript($themePath . '/javascript/searchbar.js');
		
		// css
		Requirements::css($themePath . '/css/bootstrap.min.css');
		Requirements::css($themePath . '/css/screen.css');
}

// used in footer
public function CurrentYear() {
	return date('Y');
}
````

If you change the name of the theme, perform a global replace on 'govtmin' within the theme directory.
