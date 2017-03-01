---
layout: default
title: Sqlite
---

# SQLite #

SQLite is a single-file database which follows the zero-configuration approach.
It is furthermore easy to use and is thus perfect for your first experiments with liquibase.

There is a jdbc driver available here: [https://bitbucket.org/xerial/sqlite-jdbc/downloads/](https://bitbucket.org/xerial/sqlite-jdbc/downloads/) or build from the latest sources [https://github.com/xerial/sqlite-jdbc/](https://github.com/xerial/sqlite-jdbc/)

To use sqlite with liquibase you will need the following information:

**jars for the classpath:**
 * sqlitejdbc-v&lt;version&gt;.jar

**jdbc driver name:**
 * org.sqlite.JDBC

**jdbc url:**
 * jdbc:sqlite:&lt;database-name&gt;

There is no need to create a database before you can use sqlite, as I said: it follows the zero-configuration approach.

A run of liquibase with sqlite, having the sqlite.jar and the in the current directory (and the liquibase.jar at hand as well), could look like this:

{% highlight sh %}
    java -jar liquibase.jar 
         --classpath=sqlitejdbc-v<version>.jar 
         --driver=org.sqlite.JDBC 
         --url="jdbc:sqlite:exampledb.sqlite" 
         --changeLogFile=db-changelog.xml 
         migrate
{% endhighlight %}

Tip: There is an easy to use firefox extension which can be used to display and edit a sqlite database.
Find it over here: [https://addons.mozilla.org/de/firefox/addon/sqlite-manager/](https://addons.mozilla.org/de/firefox/addon/sqlite-manager/)

Have fun :)
