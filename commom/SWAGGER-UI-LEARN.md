## swagger-ui的一些知识

## Swagger接口分类与各元素排序问题详解：
其他详细介绍 [参考地址](http://blog.didispace.com/spring-boot-learning-21-2-4/)  

* 简介：
返回实体可以通过在position参数调整界面参数显示的位置
````
@ApiModelProperty(value = "主键id", position = 1)
````

## swaggerui 如何返回list<Object>文档对象
1、返回list<object>,代码例如：
````
@Data
@EqualsAndHashCode(callSuper = false)
@Accessors(chain = true)
@ApiModel(value = "AppSearchUsersListVo", description = "位置分组list对象")
public class AppSearchUsersListVo extends AbstractList<AppUsersVo> {
    @Override
    public AppUsersVo get(int index) {
        return null;
    }

    @Override
    public int size() {
        return 0;
    }
}
````

## 常见问题
### 1、swaggerui返回文档实体类不显示？
&emsp;&emsp;主要是这个实体类没有在@ApiOperation的response中使用，所以就不会显示。例如返回list\<User>，如果User对象没有用起来，那么返回文档就不会显示list中
的User对象，处理：就直接加一个无用的controller，在@ApiOperation中response用User对象就可以了。这样list对象中的User就会显示了