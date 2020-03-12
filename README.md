# Introduction
Create wordpress plugin `mentors` that display various database queries the custom plugin should be displayed from the existing [starter-wp-theme (page.php)](https://github.com/boomcamp/starter-wp-theme/blob/master/mytheme/page.php)

The connection class 

```
<?php 

/**
 * You need to use this starter class to instantiate new database connection
 */

class Connection
{
	protected $myNewdb;

	public function __construct($username, $password, $database, $host)
	{
		$this->myNewdb = new wpdb($username, $password, $database, $host);
	}

	public function getConnection() {
		return $this->myNewdb;
	}
}

if( class_exists('Connection') ) {
    $conn = new Connection('root', '', 'mentor_db', '127.0.0.1');
}

/**
 * Continue your plugin code here..
 */

?>
```
# Database

* The plugins should be connected to the new connection class

Entities:

```
* User details = id, fullname, contact, address, email
* Course table = id , name
* Mentors table = id, user_id, course_id
* Students table = id, user_id, mentor_id
```

# Requirements

* Using [shortcode attributes](https://pippinsplugins.com/shortcodes-101-shortcode-attributes/) display the mentors detail and the students handled by the mentor e.g `[mentor name="jino" course="PHP"]`

Example query result:

```
Mentor: Jino
Course: PHP Fall 2020

Students Handle:
	1.) Jaako Andes
	2.) Seatiel Austria
	3.) Jude Agagad
	4.) Micko Matamorosa
```

* Use ` WP_Query` object to get custom `Mentors Page` and its contents and display it to `page.php`

Example query by using the page slug:

```
$pages = get_pages();
foreach ( $pages as $page ) {
  //your code to assign the $mentors-page
}


$mentor_page = WP_Query("pagename=$mentors-page');

//Continue the loop here..
```

* Should also have A WAY to insert, update using a custom [form](https://www.kvcodes.com/2014/06/how-to-create-custom-forms-in-wordpress-without-using-plugins/)

* or Should also have a WAY to delete a student handled. 

* Display shortcode inside custom theme by using `do_shortcode()` function.

Example:

```
<?php echo do_shortcode('[mentor name="jino" course="PHP"]'); ?>
```

# Finished

Submit the following to Google Classroom assignment related to this project.

Link to your repository 

* The `mentors.zip` plugin.
* The database of the project
* The forked of your updated `starter-wp-theme`
