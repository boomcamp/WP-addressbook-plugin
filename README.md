# Introduction
Create wordpress plugin `mentors` that display various database queries the custom plugin should be displayed from the existing [starter-wp-theme (page.php)](https://github.com/boomcamp/starter-wp-theme/blob/master/mytheme/page.php)

The connection class 

```
<?php 

/**
 * You need to use this starte class
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

* The plugins connection should be a new instance object of connection class

* Course table = id , name

* Mentors table = id, course_id, fullname, address, contact, email

* Students table = id, mentor_id, fullname

# Requirements

* Using [shortcode attributes](https://pippinsplugins.com/shortcodes-101-shortcode-attributes/) display the mentors detail and the students handled by the mentor e.g `[mentor name="jino" course="PHP"]`

```
Mentor: Jino
Course: PHP Fall 2020

Students Handle:
	1.) Jaako Andes
	2.) Seatiel Austria
	3.) Jude Agagad
	5.) Micko Matamorosa
```

* Use ` WP_Query` object to get your new page id and display the contents to `page.php`
