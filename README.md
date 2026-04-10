# Clearmin Web Template

![Clearmin template](preview.png)

Bootstrap 5 dashboard / webapp / admin template

> Originally a Bootstrap 3 template by Paomedia. Converted to Bootstrap 5.3.4 by Axara Technologies.

**Check the original demo : http://cm.paomedia.com/**

**More doc inside the repo**

Browser support : Chrome, Firefox, Opera, Safari, Edge, mobile browsers


## Quick start

To start using Clearmin template in a new project you can use this minimal template :
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.4/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="assets/css/bootstrap-clearmin.min.css">
    <link rel="stylesheet" type="text/css" href="assets/css/roboto.css">
    <link rel="stylesheet" type="text/css" href="assets/css/material-design.css">
    <link rel="stylesheet" type="text/css" href="assets/css/small-n-flat.css">
    <link rel="stylesheet" type="text/css" href="assets/css/font-awesome.min.css">
    <title>Clearmin Page</title>
  </head>
  <body class="cm-no-transition cm-1-navbar">
    <div id="cm-menu">
      <nav class="cm-navbar cm-navbar-primary">
        <div class="cm-flex"><div class="cm-logo"></div></div>
        <div class="btn btn-primary md-menu-white" data-toggle="cm-menu"></div>
      </nav>
      <div id="cm-menu-content">
        <div id="cm-menu-items-wrapper">
          <div id="cm-menu-scroller">
            <ul class="cm-menu-items">
              <li class="active"><a href="#" class="sf-house">This page is active</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <header id="cm-header">
      <nav class="cm-navbar cm-navbar-primary">
        <div class="btn btn-primary md-menu-white d-md-none" data-toggle="cm-menu"></div>
        <div class="cm-flex"><h1>Put your title here</h1></div>
      </nav>
    </header>
    <div id="global">
      <div class="container-fluid">
        <div class="card">
          <div class="card-body">
            <h2 style="margin:0">Hello World !</h2>
          </div>
        </div>
      </div>
      <footer class="cm-footer"><span class="float-end">&copy; ACME Inc.</span></footer>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/jquery@3.7.1/dist/jquery.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.4/dist/js/bootstrap.bundle.min.js"></script>
    <script src="assets/js/clearmin.min.js"></script>
  </body>
</html>
```

## General structure

### CSS and JS files

**CSS files (`<head>`) — load in this exact order :**

*   Bootstrap 5.3.4 CDN — `https://cdn.jsdelivr.net/npm/bootstrap@5.3.4/dist/css/bootstrap.min.css`
*   assets/css/bootstrap-clearmin.min.css (Clearmin layout — sidebar, header, navbar positioning. Must load AFTER Bootstrap 5)
*   assets/css/roboto.css (main font)
*   assets/css/material-design.css (material design svg icons classes)
*   assets/css/small-n-flat.css (small-n-flat svg icons classes)
*   assets/css/font-awesome.min.css (iconic font classes)

> **Important:** `bootstrap-clearmin.min.css` is NOT a Bootstrap 3 file. It is Clearmin's own layout stylesheet and must always be included. It must load after the Bootstrap 5 CDN so it can override where needed.

**Javascript files (just before `</body>`) — load in this exact order :**

*   jQuery 3.7.1 CDN — `https://cdn.jsdelivr.net/npm/jquery@3.7.1/dist/jquery.min.js` (required by clearmin.min.js)
*   Bootstrap 5.3.4 bundle CDN — `https://cdn.jsdelivr.net/npm/bootstrap@5.3.4/dist/js/bootstrap.bundle.min.js`
*   assets/js/clearmin.min.js (required by clearmin)

**Removed from original Bootstrap 3 version:**

*   ~~assets/js/lib/jquery.min.js~~ — replaced by jQuery 3.7.1 CDN
*   ~~assets/js/bootstrap.min.js~~ — replaced by Bootstrap 5.3.4 bundle CDN
*   ~~assets/js/jquery.mousewheel.min.js~~ — no longer needed
*   ~~assets/js/jquery.cookie.min.js~~ — replaced with localStorage in clearmin.min.js
*   ~~assets/js/fastclick.min.js~~ — obsolete, no longer needed for modern mobile browsers


### Bootstrap 3 to Bootstrap 5 class changes

The following BS3 classes have been updated throughout the template:

| Bootstrap 3 | Bootstrap 5 |
|---|---|
| `hidden-md hidden-lg` | `d-md-none` |
| `visible-xs-block` | `d-block d-sm-none` |
| `pull-right` | `float-end` |
| `pull-left` | `float-start` |
| `panel panel-default` | `card` |
| `panel-body` | `card-body` |
| `panel-heading` | `card-header` |
| `panel-footer` | `card-footer` |
| `data-toggle="dropdown"` | `data-bs-toggle="dropdown"` |
| `data-dismiss` | `data-bs-dismiss` |
| `data-target` | `data-bs-target` |
| `img-responsive` | `img-fluid` |

> **Note:** Clearmin's own `data-toggle="cm-menu"` has NOT been changed — this is Clearmin's internal toggle, not Bootstrap's.

### Menu state preservation

Menu state is now saved using `localStorage` instead of cookies (the jquery.cookie plugin has been removed).

*   **Client-side:** `.cm-menu-toggled` is automatically added to the body when needed via localStorage
*   **Server-side (recommended):** Check for `localStorage` key `cm-menu-toggled` with value `"true"` and add `.cm-menu-toggled` class to the body tag


### Body classes

*   `cm-no-transition` : **must** be present to prevent certain browsers starting transitions on page load
*   `cm-1-navbar` : when one navbar is present on your page
*   `cm-2-navbar` : when two navbars are present on your page
*   `cm-3-navbar` : when three navbars are present on your page
*   `cm-menu-toggled` : if you want the menu to be toggled on page load


## Credits

*   [Bootstrap 5](https://getbootstrap.com/) css front-end framework
*   [jQuery](http://jquery.com/) fast, small, and feature-rich JavaScript library
*   [Font Awesome](http://fortawesome.github.io/Font-Awesome/) The iconic font and CSS toolkit
*   [Roboto](https://www.google.com/fonts/specimen/Roboto) Google font
*   [Small-n-flat icons](https://github.com/paomedia/small-n-flat) SVG icons on a 24px grid
*   [Material Design Icons](https://github.com/google/material-design-icons) Google SVG icons
*   [Summernote](http://hackerwins.github.io/summernote/) Super Simple WYSIWYG Editor on Bootstrap
*   [D3.js](http://d3js.org/) Data-Driven Documents
*   [C3.js](http://c3js.org/) D3-based reusable chart library
