# Careerbook Front End Assignment

Front End Web Development using Vuejs

### Language And Framework Use

| Type          | Framework     | Version       |
| ------------- | ------------- | ------------- |
| Task Runner   | Gulp          | 4.0.2
| Module Bundler| Webpack       | 4.39.2
| HTML Templating Engine | Pug      | Differ
| CSS Preprocessor | SCSS | Differ
| Javascript Framework | Vuejs & Jquery |
| Icon Framework | Frontawesome Free |

* Differ - Each gulp and webpack use different version

### Getting Started

Make sure you have NodeJS installed (currently built using v4^).

1. Clone the repo.
2. `cd` into the folder and do a fresh `npm i`.
3. Run `gulp` to start the server

Server Configuration is point at `localhost:8080`!

The port `:8080` will auto changes if detected other Gulp / NodeJS instances.

When serve. Gulp will delete the folder/file first and create a new one.

## Note

### Gulp
 - Delete all the file in build folder first before proceed to compile all the file back to newer version.
 - Each build serve new file folder.
 - Compile all .pug file into .html file.
 - Compile all .scss file into .css file.
 - Stream Webpack file config to compile vuejs.

### Webpack
 - Each page is separate into its own js file.
 - Each page has its own vuejs file and entrypoint js.
 - Each page will be separate into local and global components
 - Local components as the name suggested is accessible only on it own entrypoint.
 - Will global components can be accessible by all pages.
 - Compile .pug inside .vuejs file.
 - Compile .scss inside .vuejs file.
