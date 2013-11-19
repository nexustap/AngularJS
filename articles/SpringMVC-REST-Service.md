SpringMVC 的restful 服务 开发,和设计
===

目前基于SpringMVC的技术架构在企业技术里面很流行.很多项目,都基于之类来构建后台架构.
我使用简化版本的SpringMVC,只是用了MVC,快速设计和开发Restful的服务而已.
什么是Model,什么是View,我都布关心,我只关心出数据服务(REST).
比如如下代码:
```java
@RequestMapping(value = "/echo", method = RequestMethod.GET)
@ResponseBody
public String echo(){
	
	return "{ status:0, describe:'ok' } ";
	
	
}
```
	
请求的是 url是  /echo 的服务.Method是 GET,返回的是整个ResponseBody.
所以我返回的json 就是 这个string 类型的.
如此简单,其他的配置文件,都采用默认配置,用标注,自动加载各种bean.

另外我还提供改进版本的方式,我引入了 Groovy,进行简化编程.
我可以提供一个Controller:


```java
@Controller
class UserRest {
	@RequestMapping("/user")
	public @ResponseBody String getUser() {
		return """
		{
			"name":"bingo",
			"age":34,
			"address":"nanjing"
		}
		""";
	}
}
```
