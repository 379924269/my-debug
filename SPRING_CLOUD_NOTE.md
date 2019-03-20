## 学习springcloud oauth2遇到的问题

#### 一、yml配置*问题：
低版本的springcloud直接用 *，高版本的用 '*'

### 二、token的问题
 * token的获取需要的参数及格式例如：
````
String xx = new BASE64Encoder().encode("clientId:clientSecret".getBytes());
List param = new ArrayList();
param.add(new BasicNameValuePair("grant_type", "password"));
param.add(new BasicNameValuePair("username", "fzp"));
param.add(new BasicNameValuePair("password", "123456"));
Header header = new BasicHeader("Authorization", "Basic " + xx);
String url = 服务器地址 + "/oauth/token";
````
 * 刷新token的使用：
````
String xx = new BASE64Encoder().encode("clientId:clientSecret".getBytes());
List param = new ArrayList();
param.add(new BasicNameValuePair("grant_type", "refresh_token"));
param.add(new BasicNameValuePair("refresh_token", "refresh_token 获取token是获得的"));
Header header = new BasicHeader("Authorization", "Basic " + xx);
String url = 服务器地址 + "/oauth/token";
````

 * 验证token的使用：
````
String xx = new BASE64Encoder().encode("clientId:clientSecret".getBytes());
List param = new ArrayList();
param.add(new BasicNameValuePair("grant_type", "refresh_token"));
param.add(new BasicNameValuePair("token", "token"));
Header header = new BasicHeader("Authorization", "Basic " + xx);
String url = 服务器地址 + "/oauth/check_token";
````
 * token调用普通接口：
````
 header中要加参数："Authorization", "bearer token");
````
### 三、security密码问题，springcloud高版本需要加密，解决方法
 * 在安全配置中（MySecurityConfiguration）添加一个bean
````
    @Bean
    public static NoOpPasswordEncoder passwordEncoder() {
        return (NoOpPasswordEncoder) NoOpPasswordEncoder.getInstance();
    }
````
 * 在安全配置中（MySecurityConfiguration）添加一个bean
````
    @Bean
    public static NoOpPasswordEncoder passwordEncoder() {
        return (NoOpPasswordEncoder) NoOpPasswordEncoder.getInstance();
    }
````
### 三、security密码问题，springcloud高版本需要加密，解决方法

