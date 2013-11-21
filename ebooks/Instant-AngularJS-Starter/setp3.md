

步骤3 -配置指南应用AngularJS 
我们将开始AngularJS的配置文件，Guidebook.html和Guidebook.js的。这是我们将定义应用程序的结构，包括我们的模型和控制器。首先第一件事情，让我们进入Guidebook.html，我们将在这里开始我们的文件结构：

    <！DOCTYPE HTML> <html ng-app='Guidebook'> <HEAD> <脚本的src ='http://ajax的.googleapis.com / Ajax /库/ angularjs/1.0.2/angular.js的'> </ SCRIPT> src='Guidebook.js'> 
     <script src='controller/ChapterController.js'> </ SCRIPT> <script src='controller/NotesControllers.js'> </ SCRIPT> <script src='model/NoteModel.js'> </ SCRIPT> <script src='model/ChapterModel.js'> </ SCRIPT> <link rel='stylesheet'的href='view/styles.css'> <AngularJS入门指南</ TITLE> </ HEAD> <BODY> <H1>欢迎AngularJS入门指南</ H1> <股息NG视图> <！ -点击此处添加在运行时。- > </ DIV> </ BODY> </ HTML>



一些看起来很熟悉。我们有我们的DOCTYPE，我们包括AngularJS，我们有相应的注解。我们也包括我们的模型和控制器文件，但没有视图文件（视图映射通过JavaScript，我们会在一分钟内）。请注意，这个时候，我们正在定义一个名称为ng-app annotation注释。这是没有必要的，因为我们看到最后一个例子，但对于现实世界的应用，这是一个好主意，因为它可以帮助我们的模型和控制器命名。（如果我们有两个AngularJS应用程序在同一页上，单独的模块，将帮助我们记住哪些组件属于哪个应用程序）。我们也有一个新的注释：NG-视图。这告诉AngularJS，哪里需要加载我们的视图。NG视图只能有一个实例，它应该包含我们要在应用程序中动态加载和改变的一切。如果东西所在NG视图之外，像我们前面的例子中的标题，这将是在任何时候都可见。
让我们回到Guidebook.js,指定我们的视图映射:

    var guidebookConfig = function($routeProvider) {
    $routeProvider
    .when('/', {
    controller: 'ChaptersController',
    templateUrl: 'view/chapters.html'
    })
    .when('/chapter/:chapterId', {
    controller: 'ChaptersController',
    templateUrl: 'view/chapters.html'
    })
    .when('/addNote/:chapterId', {
    controller: 'AddNoteController',
    templateUrl: 'view/addNote.html'
    })
    .when('/deleteNote/:chapterId/:noteId', {
    controller: 'DeleteNoteController',
    templateUrl: 'view/addNote.html'
    })
    ;
    };
    var Guidebook = angular.module('Guidebook', []).
    config(guidebookConfig);

让我们看上文中的最后一行。看看是如何定义一个AngularJS的命名空间，我们称为模块（我们后面将讨论更多关于模块的话题）。通过这种方式，我们可以保证我们的控制器和数据模型在他们的命名空间范围内起效，这是一个最好的做法，尤其是重要的，这个应用可以加到其它的页面中与其它内容共存
同样你看，我们绑定一个路由配置在我们的应用中，路由给控制器一个url，并通过模板展示出，控制器需要的参数是url的一部份，例如，如果我们访问http://your-webserver/guidebook.html#/chapter/2 ，angularjs加载chapters.html 页面，并传chapter/2 参数给控制器
当我们要删除一个便笺，比如第一章中的第四章节，我们会加载一个url，后面加上#/deleteNode/1/4.,那控制器就会把此章的1到4的章节删掉
路由的知识点其实比我们上面讲的点要多，比如，上面的例子是直接去访问一个有效的链接，路由也支持前进和后退的导航，这意味着用户只要点击浏览器中的前进和后退按钮，AngularJS将返回到最近的内部网址，而不是完全退出应用程序。 
路由是一个简单，功能强大的一个angularjs的内部应用，即使是一个很长的路由列表，这比散列在多个文件中的逻辑管理方式要更好,在这一点上，我们为我们的应用配置少量的路由，然后告诉angularjs控制器何时加载它们，同时告诉控制器加载视图，现在让我们建立一些视图

