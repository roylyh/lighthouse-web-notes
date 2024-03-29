# Smart Campus

## Backend Tech stack
SpringBoot[SpringMVC], MybatisPlus[Mybatis], swagger2
Maven, Tomcat, Mysql, Sqlyog

## Git
1. intall Git.exe  
2. IDEA - Setting - Version Control - Git
3. SSH Key GITHUB - PUB Key IDEA - Setting - Version Control - SubVersion - Private Key
4. Git - Push - Define Remote (ssh address from github)

## JDK + IDEA + MAVEN + TOMCAT
JDK 8
MAVEN  Buid, Execution, Deployment - Build Tools - Maven
If integerated in the IDEA, MAVEN's Environment Variable is not necessary.
TOMCAT is integerated in the IDEA.

## Lombok + MyBatisX + MyBatisPlus
Settings - Plugins (Lombok + MyBatisX + MyBatisPlus)  
Build, Execution, Deployment - Compiler - Annotation Processors (Enable annotation processing - To enable Lombok)

## pom file
The spring-boot-starter-parent project is a special starter project that provides default configurations for our application and a complete dependency tree to quickly build our Spring Boot project.  
Once we've declared the starter parent in our project, we can pull any dependency from the parent by just declaring it in our dependencies tag. We also don't need to define versions of the dependencies; Maven will download jar files based on the version defined for the starter parent in the parent tag.
```xml
<parent>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-parent</artifactId>
  <version>2.2.1.RELEASE</version>
  <relativePath/> <!-- lookup parent from repository -->
</parent>
```

## application.yml

## config class
1. MpConfig - paginationInterceptor
2. Swigger2Config - Swigger2

## util class
1. CreateVerifiCodeImage
2. JwtHelper - token
3. AuthContextHolder - parse the token in the request
4. MD5
5. Result - JSON response encapsulation
6. ResultCodeEnum - enum
7. UploadFile

## POJO class
(Lombok & MybatisPlus)
1. Admin
2. Grade ...

## Mapper Interface
```java
@Repository
public interface AdminMapper extends BaseMapper<Admin> {
}
```

## Service Interface
```java
public interface AdminService extends IService<Admin> {
    Admin login(LoginForm loginForm);

    Admin getAdminById(Long userId);

    IPage<Admin> getAllAdmin(Page<Admin> pageparam, String adminName);
}
```

## Service Impl Class
```java
public class AdminServiceImpl extends ServiceImpl<AdminMapper, Admin> implements AdminService  {

    @Override
    public Admin login(LoginForm loginForm) {
        QueryWrapper<Admin> QueryWrapper = new QueryWrapper<>();
        QueryWrapper.eq("name",loginForm.getUsername());
        String encrypt = MD5.encrypt(loginForm.getPassword());
        QueryWrapper.eq("password",encrypt);
        Admin admin = baseMapper.selectOne(QueryWrapper);
        return admin;
    }
}    
```

## Controller Class
```java
@RestController
@RequestMapping("/sms/adminController")
public class AdminController {

    @Autowired
    private AdminService adminService;
    // GET http://localhost:9002/sms/adminController/getAllAdmin/1/3?    adminName=a
    @GetMapping("/getAllAdmin/{pageNo}/{pageSize}")
    public Result getAllAdmin(
            @PathVariable("pageNo") Integer pageNo,
            @PathVariable("pageSize") Integer pageSize,
            @RequestParam(value = "adminName",required = false) String adminName
    ) {
        Page<Admin> pageparm = new Page<Admin>(pageNo, pageSize);
        IPage<Admin> Ipage = adminService.getAllAdmin(pageparm,adminName);
        return Result.ok(Ipage);
    }
}
``