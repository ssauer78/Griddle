Griddle
=======
This is  a fork of the [Griddle table](https://github.com/GriddleGriddle/Griddle) in version 0.5


Griddle is a simple grid Component for use with React. It depends on [Lodash Modules](https://lodash.com/) and [React](http://facebook.github.io/react/).

Please check out the original [documentation and examples](http://dynamictyped.github.io/Griddle).

I did some changes that where needed for our use.

1. The pageSize is now set correctly if useExternal is set.
2. The defaultColSpan is now set even though 'useGriddleStyles' is set. This had to be done because the loading content was only shown in the first column of the table and not spread throughout the full table.  
3. Moving the pagingContent out of the main table and change it to a div. This was needed because in wide tables, the paging content was not visible anymore because it had the same size as the table.
4. Added a componentWillUpdate call to griddle. In our case the griddle was initialized first without any results because they were fetched asynchronously. Therefor the columnMetadata was only initialized empty and even though we gave it in a later state, this was not updating the settings section of the griddle table.
