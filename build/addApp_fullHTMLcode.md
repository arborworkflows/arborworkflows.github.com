---
layout: page
title: Create a new Arbor app.
permalink: /build/addApp_fullHTMLcode.html/
---

Full html code for simmap app. [back to directions]({{ site.baseurl }}/build/addApp.html)


```html
<!doctype html>
<html>
    <head>
        <title>PGLS for two variables (X versus Y)</title>
        <link href=//netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap-glyphicons.css rel=stylesheet>
        <link rel="stylesheet" href="//fonts.googleapis.com/css?family=Droid+Sans:400,700">
        <link rel="stylesheet" href="../static/built/fontello/css/fontello.css">
        <link rel="stylesheet" href="../static/built/girder.ext.min.css">
        <link rel="stylesheet" href="../static/built/fontello/css/fontello.css">
        <link rel="stylesheet" href="../static/built/app.min.css">
        <link rel="stylesheet" href="../static/built/plugins/flow/flow.ext.min.css">
        <link rel="stylesheet" href="css/arbortools.css">
        <style>

html, body {
    height: 100%;
}
#upload, #help {
    width: 100%;
    padding: 20px;
}
#editor, #vis {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
.spacer {
    margin-top: 20px;
}
.draggable {
    text-align: center;
    padding: 10px;
}

<!-- Select Y column -->
#column-input {
    padding: 50px;
}

.full-width {
    width: 100%;
}
#analyze {
    padding-top: 20px;
    padding-bottom: 20px;
}
        </style>
    </head>
    <body>

        <nav class="navbar navbar-default navbar-static-top" id="nav" role="navigation">
            <div class="container-fluid">
                <div class="navbar-header">
                    <a class="navbar-brand" href="#">
                        <img src="../static/img/Arbor.png" height="35px" alt="Arbor Logo">
                    </a>
                    <a class="navbar-text" href="#">
                      Arbor App:
                    </a>
                    <a class="navbar-text" href="#">
                      Simmap
                    </a>
                </div>
            </div>
        </nav>

        <div class="panel-group">
          <div class="panel panel-default">
            <div class="panel-heading">
              <h4 class="panel-title">
                <a data-toggle="collapse" href="#collapse1"><b>Click here </b> for more information about stochastic character mapping</a>
              </h4>
            </div>
            <div id="collapse1" class="panel-collapse collapse">
              <div class="panel-body">
                <b>Stochastic character mapping</b> is ...
              </div>
              <div class="panel-footer">More info <a href = "http://phylogeneticcomparativemethods.com">textbook</a></div>
            </div>
          </div>
        </div>

        <div class="container-fluid">
            <div class="row">
                <div class="col-sm-3">
                    <div class="btn btn-default" id="help" data-toggle="button">Show help</div>
                    <div id="column-names" class="btn-group-vertical full-width btn"></div>
                </div>
                <div class="col-sm-9">
                        <div id="dataset-management">
                            <div class="btn btn-primary full-width" id="upload">
                                <i class="glyphicon glyphicon-file"></i> Browse or drop files here
                            </div>
                            <div class="form-group hide">
                                <input id="g-files" type="file" multiple="multiple">
                            </div>
                            <div class="form-inline">
                                <select class="form-control datasets hidden"></select>
                            </div>
                        </div>
                        <div class="col-sm-8 spacer full-width">
                            <p id="tree-name"class="text-justify">
                                Tree: (none)
                                <span class="glyphicon glyphicon-exclamation-sign"></span>
                            </p>
                            <p id="table-name" class="text-justify">
                                Table: (none)
                                <span class="glyphicon glyphicon-exclamation-sign"></span>
                            </p>
                        </div>



                      <div class="btn-group">


                        <div id="column-input" class="bg-warning btn spacer">
                            Load data above to proceed
                        </div>

                      </div>

                        <div id="analyze" class="btn btn-success spacer disabled full-width">
                            Go!
                        </div>
                        <div id="notice" class="spacer text-center"></div>
                </div>
            </div>
            <div class="row hidden spacer" id="input-table-vis-container">
                <div class="col-sm-3">
                    <div class="btn btn-default full-width" id="table-preview">
                        <i class="glyphicon glyphicon-folder-open" id="table-preview-icon"></i>
                        <span id="table-preview-text"> Hide input table preview</span>
                    </div>
                    <div class="spacer" id="input-table-vis"></div>
                </div>
            </div>

            <div class="row">
                <div id="result" class="col-sm-12 full-width">
                </div>
            </div>
            <div class="row">
                <div id="model-plot" class="col-sm-12 text-center">
                </div>
            </div>
        </div>
        <div id="vis" class="hidden"></div>
        <div id="code-editor" class="hidden"></div>
        <div id="template-container" class="hidden"></div>
        <script src="../static/built/plugins/flow/libs.min.js" charset="utf-8"></script>
        <script src="../static/built/plugins/flow/ace.min.js" charset="utf-8"></script>
        <script src="../static/built/app.min.js" charset="utf-8"></script>
        <script src="../static/built/plugins/flow/app.min.js" charset="utf-8"></script>
        <script src="js/main.js" charset="utf-8"></script>
    </body>
</html>
```
