#### idea 注释模板

* 类注释模板

  > File | Settings | Editor | File and Code Templates
  >
  > 修改Class、Interface、Enum、AnnotationType注释模板
  >
  > 以下所示的${DESCRIPTION}是自定义变量，会在创建类时请求输入

  ```java
  /**
   * @Description ${DESCRIPTION}
   * @Auther ${USER}
   * @DateTime ${DATE} ${TIME}
   */
  ```

* 方法注释模板

  > File | Settings | Editor | Live Templates下添加自定义Template Group，并在自定义Template Group下添加自定义Template 
  >
  > `Abbreviation:* `(* 对应注释快捷键 * + Tab)
  >
  > ``````java
  > /**
  >  * 功能描述: <br>
  >  *〈$END$〉
  >  $param$
  >  * @Return:$return$
  >  * @Author:$user$
  >  * @Date: $DATE$ $TIME$
  >  */
  > ``````
  >
  > Edit Template Variables参数部分Expression内容如下:
  >
  > return - methodReturnType()
  >
  > date - date()
  >
  > time - time()
  >
  > 这个是param这个参数名的Expression:
  >
  > ```
  > groovyScript("def result=''; def params=\"${_1}\".replaceAll('[\\\\[|\\\\]|\\\\s]', '').split(',').toList(); for(i = 0; i < params.size(); i++) {result+='* @param ' + params[i] + ((i < params.size() - 1) ? '\\n ' : '')}; return result", methodParameters())
  > ```