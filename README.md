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
 * Continue your code here..
 */

?>
```
# Database

* The plugins should be connected to the new connection class

Entities:

```
* Course table = id , name
* Mentors table = id, course_id, fullname, address, contact, email
* Students table = id, mentor_id, fullname
```

# Requirements

* Using [shortcode attributes](https://pippinsplugins.com/shortcodes-101-shortcode-attributes/) display the mentors detail and the students handled by the mentor e.g `[mentor name="jino" course="PHP"]`

Example output:

```
Mentor: Jino
Course: PHP Fall 2020

Students Handle:
	1.) Jaako Andes
	2.) Seatiel Austria
	3.) Jude Agagad
	5.) Micko Matamorosa
```

* Use ` WP_Query` object to get custom `Mentors Page` and its contents and display it to `page.php`

Example query by using the page slug:

```
$pages = get_pages();
foreach ( $pages as $page ) {
  //your code to assign the $mentors-page
}


$mentor_page = WP_Query("pagename=$mentors-page');

```

* Should also have A WAY to insert, update and delete a student handled by a mentor in a cohort. 

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
