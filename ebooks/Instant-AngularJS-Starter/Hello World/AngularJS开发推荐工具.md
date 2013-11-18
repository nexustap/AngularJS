AngularJS开发推荐工具 
---------------------
最低的限度，建立一个AngularJS的应用你只需要以下两个工具：

 - 一个文本编辑器
 - 一个Web浏览器

但如果我们想建立伟大的事情，我们将需要伟大的工具，没有最低限度。

AngularJS是一个对于正式开发和有正式开发工具的认真开发者的严肃框架。

让我们重温列表：

 - 一个文本编辑器
 - 一个良好的网络浏览器
 - 一个Web服务器
一个良好的网络浏览器应该有一个综合性的检查器和调试器，应该支持现代的HTML / JavaScript功能。所有主流浏览器的最新版本符合这些条件，所以只是确保你喜欢的浏览器是最新的。

例如，我目前使用的是OSX的最新版本的谷歌Chrome浏览器，其开发工具打开，它看起来像下面的截图：
![alt text](./images/0-1.jpg "Title")
一旦你有好的编辑器和浏览器，你需要一个地方来测试你的工作。为此，您可以直接在浏览器，但我要强烈建议您使用Web服务器有两个原因：

 - 现代浏览器不喜欢直接从您的硬盘驱动器运行文件,并且直接从磁盘运行时经常会限制你的应用程序。
 - 当你的应用程序开发完成，并公布给真实的客户使用和喜爱，它是要运行在Web服务器上。在非常类似于你的用户将会看到的环境中测试您的应用程序，它总是一个好主意。

设置本地Web服务器是不是特别困难，并有几个AngularJS的友好的工具，可以使您更容易设置。
Yeoman就是这样一种工具，可在https://github.com/yeoman获得。Yeoman为应用开发者提供了许多有用的功能，如应用程序开发包的管理和项目的脚手架。特别值得注意的是Yeoman服务器命令，这将启动本地Web服务器，可以承载您的AngularJS应用程序的。

angular-sprout是另一种选择，一个特定的AngularJS的自助工具。它提供了一个类似的功能集，并提供了通过Node.js（另一种有抱负的Web开发行家的方便工具）的Web服务器集成。你可以从https://github.com/thedigitalself/angular-sprout、http://nodejs.org分别得到这些工具。


  [1]: https://github.com/nexustap/AngularJS/blob/master/ebooks/Instant-AngularJS-Starter/images/0-1.jpg