### tool
    live Server以服务器运行vscode文件

### angularjs
    1.基本用法：
        a.ng-app绑定指定的dom元素
        b.ng-controller:绑定控制器，其中$scope指这个控制器的作用域
        c.js指定应用：angular.module(模块名,[外部依赖])
        d.使用控制器：app.controller(控制器名，回调函数)

    2.指令
        a.ng-app 指令初始化一个 AngularJS 应用程序
        b.ng-init 指令初始化应用程序数据
        c.ng-model 指令把元素值（比如输入域的值）绑定到应用程序。
        d.ng-repeat循环指令 ng-repeat='item in arr'

    3.自定义指令
    app.directive("myDir",function(){
        return {
            模板
            template:'<h1>测试</h1>'
        }
    })
        a.调用自定义指令的方式：
            元素名
            属性
            类名
            注释
        e.g:
            <!-- 元素名 -->
            <my-dir></my-dir>
            <!-- 类名 -->
            <div class="my-dir"></div>
            <!-- 属性 -->
            <div my-dir></div>
            <!-- 注释 -->
            <!-- my-dir -->

        b.默认的调用方式为：元素名，属性

        c.设置调用方式： restrict: EACM

    4.ng-model指令：
        a.数据双向绑定：
        b.验证用户输入
        c.CSS类
            e.g:
             /* 设置验证不通过样式 */
            input.ng-invalid { 
              background-color: lightblue;
            }

    5.scope作用域
        在创建了控制器的时候，产生$scope
        作用范围：当前的控制器范围
        根作用域：$rootScope:可以作用在 ng-app 指令包含的所有 HTML 元素中。
        rootscope 定义的值，可以在各个 controller 中使用

    6.控制器：controller

    7.过滤器：一般用于数据转换
        语法：{{值 | 过滤器名字}}  "| 为管道符"
        a.currency	格式化数字为货币格式。
        b.filter	从数组项中选择一个子集。
        c.lowercase	格式化字符串为小写。
        d.orderBy	根据某个表达式排列数组。
        e.uppercase	格式化字符串为大写。

        自定义：app.filter(name,[依赖服务，callback])

    8.服务service
        a.内建服务：是函数或者是对象
            包括40多个服务：
            $location.absUrl(),获取当前页面的地址，需要作为参数传控制器中
            $http服务：最常用的，发送请求$http.get(path).then(callback)
            $timeoout:对应window.setTimeOut()
            $interval:对应window.setInterval()

        b.自建服务
            app.service(name,callback)

    9.Http:$http核心服务
        a.读取JSON文件
    
    10.Select:选择框
        <select ng-model="selectedName" ng-options="x for x in names"></select>

    11.ng-repeat:
        a.索引：$index
        b.$odd
        c.$even

    12.SQL：

    13.Html Dom:
        ng-disbaled:Boolean
        ng-show:显示隐藏一个元素
        ng-hide:显示隐藏元素

    14.事件：事件要用()进行调用
        ng-click:点击事件

    15.模块
        创建模块：angular.module(name)

    16.表单
        a.novalidate 属性是在 HTML5 中新增的。禁用了使用浏览器的默认验证。
        b.验证：
            $dirty	表单有填写记录
            $valid	字段内容合法的
            $invalid	字段内容是非法的
            $pristine	表单没有填写记录

    17.api:全局：
        angular.lowercase()	转换字符串为小写
        angular.uppercase()	转换字符串为大写
        angular.isString()	判断给定的对象是否为字符串，如果是返回 true。
        angular.isNumber()	判断给定的对象是否为数字，如果是返回 true。

    18.属性监听：$scope.$watch(name,callback)

    19.包含：ng-include:包含HTML内容

    20.angular动画：
        a.AngularJS 使用动画需要引入 angular-animate.min.js 库

    21.依赖注入：
        核心组件：value,factory,service,provider,constant
        a.value对象，用于向控制器传递值（配置阶段）
            app.value(键，值)
            注入控制器、服务、指令等

        b.factory是一个函数，要有返回值,像一个工厂
        app.factory(name,callback)
        注入控制器、服务、指令等

        c.provider?具体用法

        d.constant:用于定义常量，
            app.constant(name,value)
            注入控制器、服务、指令等

    22.路由：可以实现单页面程序
        a.实现路由的js文件：angular-route.js
        b.ngRoute作为主应用程序的依赖模块,angular.module(name,['ngRoute'])
        c.ng-view指令，会根据路由变化显示不同的内容
        d.$routeProvider配皮路由规则
            $routeProvider.when(path,{})、otherwise({redirectTo:path})
                {}：template:简单模板
                    templateUrl：模板路径
                    controller：指定对应的控制器
                    controllerAs：控制器名称
                    redirectTo：重定向
                    resolve：指定当前controller依赖的模块

        e.app.config()定义匹配规则

    23.应用
        