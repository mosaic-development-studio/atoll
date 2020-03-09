# atoll
Generate sites from files.

## Flow

### Template development
- developed in HTML, CSS, and JS
- data attributes to signal nodes containing variables
    - data-type will equal a pre-determined data type
    - each node with a data-type will be checked for a variable
    - if there's a variable, a field for that variable type will be created
        - string reveals a text input
        - style reveals a list of style attributes
        - image reveals an upload button
        - etc
- variables are wrapped in {single} curly braces

### Template use
- a list of editable fields is created from parsing the data attributes
- user can edit text, styles, upload images, audio, and video
- click download files to download a directory containing files needed to upload template
- click deploy to deploy a new site or update a site that's already been deployed

### System compiling
- upon clicking download/deploy, a stringified version of the template HTML is populated by variables
- HTML string is piped through a gulp build task
    - comments removed
    - JS stringified
    - CSS broken into above/below the fold
    - files placed into directory
    - directory zipped
- HTML downloaded
