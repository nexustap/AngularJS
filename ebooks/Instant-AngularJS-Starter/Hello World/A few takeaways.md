A few takeaways
---------------
在我们继续之前，让我们花点时间来回顾下我们当前的成果。作为参考，这里是我们刚刚建成的完整的应用程序，： 

    <!DOCTYPE html>
    <html ng-app>
        <head>
            <script src='http://ajax.googleapis.com/ajax/libs/
            angularjs/1.0.3/angular.js'></script>
            <script>
                function Clock($scope) {
                    $scope.currentTime = new Date();
                }
            </script>
            <title>Welcome to AngularJS</title>
        </head>
        <body>
            <h1>Hello, World.</h1>
            <p ng-controller='Clock'>
                The current time is {{currentTime | date:'h:mm:ss a'}}.
            <p>
        </body>
    </html>

让我们开始写一个时钟功能。不管你信不信，这就是一个AngularJS控制器看起来的样子-简单淳朴。这里唯一真正有趣的是函数接受的`$scope`变量。在JavaScript中scope是一个麻烦的主题，但AngularJS试图通过提供自己的上下文使你的生活变得更容易，名为`$scope`。我们谈了很多有关`$scope`以后，但现在，请注意我们如何使用它，我们得到JavaScript的原生日期对象的当前日期，并将其存储在currentTime的属性，这样我们就可以在我们的应用程序的视图使用它。

通过我们放置在我们的标记注释，时钟控制器绑定到我们的用户界面。第一个注释是HTML标签，在该文件的顶部。通过识别一个ng-app标签，我们告诉AngularJS，在我们的应用程序中一切都包含在该标签。注意，你可以做任何标记，而不仅仅是HTML标签。这是非常宝贵的，如果你要把AngularJS集成到现有的应用程序，因为它让你完全控制哪些元素可供AngularJS 。在我们的例子中，我们可以把ng-app注释在body甚至是段落标记，一切仍然工作，因为在我们的标记外不使用AngularJS，直到里面的段落标记。

注解段落标记，ng-controller，是绑定我们的控制器（Clock函数）和我们的视图（段落标记里面的一切）。如ng-app一样，我们可以将这个注解向上移动到body或HTML标签。只要在旁边定义或在ng-app的子元素旁边定义，它就将工作，那么任何在旁边的或者低于ng-controller将能够被使用。

我们的应用程序中的关键是段落标记的内容。具体来说，有以下有点的AngularJS语法 ：

    {{currentTime | date:'h:mm:ss a'}}

currentTime属性是要给我们在Clock方法里设置的JavaScript日期对象的值。它旁边的那根竖线是我们告诉AngularJS我们要在显示它之前格式化该数据的一种方式。具体而言，我们使用在AngularJS内置的日期格式化，并提供一个字符串解释我们希望它如何格式化（我们也可以使用我们自己的格式化功能，但在这里没有必要这样做）。

回想一下，AngularJS其实就是整合和扩展HTML建立一个动态的应用程序。这已经在我们的简单的例子中看到，我们使用的是现有的HTML和JavaScript的实体，并使用AngularJS注释和日期过滤器增强他们。

使用这些简单的技术，AngularJS能够创建完全独立的应用程序。由于AngularJS是一个完全客户端库，与任何服务器端库整合都是非常容易，只要建立一个AJAX连接。

比我们在这里看到，AngularJS还有更多的东西提供给我们。让我们建立更大的应用！在下一节中，我们将探讨视图，控制器和模型如何携手合作，共创基于AngularJS的一个可扩展的应用架构。

