# Development

To work on the complete system with API, admin, client and templates each project's docker-compose file should be started.

The templates should be installed with the `-dev.json` file. This is done with the command in the API docker container:

````bash
bin/console app:template:load https://raw.githubusercontent.com/os2display/display-templates/develop/build/book-review/book-review-dev.json
````
