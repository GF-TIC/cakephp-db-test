Overview
========

**DbTest** plugin enables developers to speed up tests running on mysql/postgresql database.

The logic of DbTest differs from testsuite in the way that fixtures are handled.

CakePHP TestSuite uses fixtures to initialize test database, DbTest doesn't use fixtures at all.
Instead, it uses an additional template database that is initialized based on the file **config/sql/test_db.sql**

Generic cycle of test execution under DbTest
--------------------------------------------

* When test suite starts with DbTest, It loads test database from template database snapshot.
* Before test method starts, DbTest initializes the transaction.
* After test method finishes, DbTest rollbacks transaction.

This way database modifications are quickly restored, but requires that the table uses a transaction engine like InnoDb.

Support
-------

For bugs and feature requests, please use the [issues](https://git.cakedc.com/cakedc/db_test/issues) section of this repository.

Commercial support is also available, [contact us](http://cakedc.com/contact) for more information.

Contributing
------------

If you'd like to contribute new features, enhancements or bug fixes to the plugin, just read our [Contribution Guidelines](http://cakedc.com/plugins) for detailed instructions.

License
-------

Copyright 2007-2014 Cake Development Corporation (CakeDC). All rights reserved.

Licensed under the [MIT](http://www.opensource.org/licenses/mit-license.php) License. Redistributions of the source code included in this repository must retain the copyright notice found in each file.
