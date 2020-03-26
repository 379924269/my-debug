## swagger-ui的一些知识

## Swagger接口分类与各元素排序问题详解：
其他详细介绍 [参考地址](http://blog.didispace.com/spring-boot-learning-21-2-4/)  

* 简介：
返回实体可以通过在position参数调整界面参数显示的位置
````
@ApiModelProperty(value = "主键id", position = 1)
````

## swaggerui 返回参数处理   返回vo
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