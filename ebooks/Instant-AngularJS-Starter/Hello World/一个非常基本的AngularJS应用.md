一个非常基本的AngularJS应用
---------------------------
我们所有的工具到位，我们就可以开始编码！就让我们投身而入。打开你的文本编辑器，快速的插入一个HTML框架如下： 

    <!DOCTYPE html>
    <html>
     <head>
      <title>Welcome to AngularJS</title>
     </head>
     <body>
      <h1>Hello, World.</h1>
     </body>
    </html>

> 下载示例代码
您可以用您在http://www.packtpub.com的账户下载您在Packt购买的所有书籍的示例代码文件。如果您在其他地方购买了这本书，你可以访问http://www.packtpub.com/support，并注册,有电子文件直接邮寄给您。


请记住使用合适的DOCTYPE。这不是AngularJS必需的，但它是非常重要的帮助网页浏览器正确地呈现内容。说到AngularJS，现在是时候添加框架了。为此，我们将它添加到文件头，如下面的代码片段所示： 

    <head>
        <script src='http://ajax.googleapis.com/ajax/libs/
        angularjs/1.0.3/angular.js'></script>
        <title>Welcome to AngularJS</title>
    </head>

你会注意到我们从云上包含了AngularJS包，而不是下载，使用相对Url来包含它。这是非常好的 ，并建议以这种方式访问AngularJS。写这篇文章的当前版本是1.0.3，但你应该使用最新的版本AngularJS，这是可以在http://angularjs.org获取。我们还采用了非压缩后的版本，这是很好的发展，但生产，你应该使用压缩后的版本。

如果在你的网页浏览器运行我们目前的代码指向到你的web服务器，当然!你会看到一个非常基本的没有特殊AngularJS行为的HTML输出。您可以使用内置到您的浏览器的网页检查器验证AngularJS加载，但是，你可以看到，我们没有做任何事情。

让我们来修改下。首先，我们将添加一个简单的脚本到我们头上 

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

接下来，我们需要告诉AngularJS我们的应用。我们这样做是通过注解我们的HTML标签： 

    <html ng-app>

最后，我们将到一个段落标记撒上少许AngularJS戏法： 

    <body>
        <h1>Hello, World.</h1>
        <p ng-controller='Clock'>
            The current time is {{currentTime | date:'h:mm:ss a'}}.
        <p>
    </body>
    
现在，如果你运行的应用程序，你应该看到一条消息，标题下，告诉你当地时区的当前时间。它可能不是看起来不起眼，但它是你的第一AngularJS的应用程序，它为我们提供了一些重要的洞察如何建立AngularJS应用。

