# Introduction
Create wordpress plugin `mentors` that display various database queries

```
<?php 

/**
 * Do not override!
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
