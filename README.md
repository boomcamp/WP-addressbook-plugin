# Introduction

Create a wordpress plugin called `wpcrud` and implement OOP from the previous [AddressBook Refactor](https://github.com/boomcamp/PHP1-OOP-AddressBook-refactor).

### Database

- The plugin should connected on a `new wpdb()` connection class and implemented in an interface called `IDBcredentials`.

- Class `wpcrud` should be dependent in `Connection` class.

### Design

- Design layouts should be resposive, `styles` and `script` are both `enqueue` in wordpress `admin` and `public` website.

- A custom form should be used in the design.

### Functionality

- Able to create `N` records in a page using shortcode.

Example: display 5 contacts `N = 5`

```
[contacts='5']
```

- A way to display a paginated list of contact.

- A way to create new contact.

- A way to delete contact from table.

- A way to update a contact.

- A way to `activate`, `deactivate` and `delete` the plugin.


# Finished

Submit the following to Google Classroom assignment related to this project.

- Link to your repository

- The `wpcrud.zip` plugin.

- The `database` of the plugin 
