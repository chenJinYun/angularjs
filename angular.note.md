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
        e.ng-bind:与{{}}表达式一样效果

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

    指令	       描述
    ng-app	   定义应用程序的根元素。
    ng-bind	   绑定 HTML 元素到应用程序数据
    ng-bind-html	绑定 HTML 元素的 innerHTML 到应用程序数据，并移除 HTML 字符串中危险字符
    ng-bind-template	规定要使用模板替换的文本内容
    ng-blur	     规定 blur 事件的行为
    ng-change	 规定在内容改变时要执行的表达式
    ng-checked	 规定元素是否被选中
    ng-class	 指定 HTML 元素使用的 CSS 类
    ng-class-even	类似 ng-class，但只在偶数行起作用
    ng-class-odd	类似 ng-class，但只在奇数行起作用
    ng-click	 定义元素被点击时的行为
    ng-cloak	 在应用正要加载时防止其闪烁
    ng-controller	定义应用的控制器对象
    ng-copy	      规定拷贝事件的行为
    ng-csp	      修改内容的安全策略
    ng-cut	      规定剪切事件的行为
    ng-dblclick	  规定双击事件的行为
    ng-disabled  	规定一个元素是否被禁用
    ng-focus	规定聚焦事件的行为
    ng-form	    指定 HTML 表单继承控制器表单
    ng-hide	    隐藏或显示 HTML 元素
    ng-href	    为 the <a> 元素指定链接
    ng-if	    如果条件为 false 移除 HTML 元素
    ng-include	在应用中包含 HTML 文件
    ng-init	    定义应用的初始化值
    ng-jq	    定义应用必须使用到的库，如：jQuery
    ng-keydown	规定按下按键事件的行为
    ng-keypress	规定按下按键事件的行为
    ng-keyup	规定松开按键事件的行为
    ng-list	    将文本转换为列表 (数组)
    ng-model	绑定 HTML 控制器的值到应用数据
    ng-model-options	规定如何更新模型
    ng-mousedown	规定按下鼠标按键时的行为
    ng-mouseenter	规定鼠标指针穿过元素时的行为
    ng-mouseleave	规定鼠标指针离开元素时的行为
    ng-mousemove	规定鼠标指针在指定的元素中移动时的行为
    ng-mouseover	规定鼠标指针位于元素上方时的行为
    ng-mouseup	    规定当在元素上松开鼠标按钮时的行为
    ng-non-bindable	规定元素或子元素不能绑定数据
    ng-open	        指定元素的 open 属性
    ng-options	    在 <select> 列表中指定 <options>
    ng-paste	    规定粘贴事件的行为
    ng-pluralize	根据本地化规则显示信息
    ng-readonly	    指定元素的 readonly 属性
    ng-repeat	    定义集合中每项数据的模板
    ng-selected	    指定元素的 selected 属性
    ng-show	        显示或隐藏 HTML 元素
    ng-src	        指定 <img> 元素的 src 属性
    ng-srcset	    指定 <img> 元素的 srcset 属性
    ng-style	    指定元素的 style 属性
    ng-submit	    规定 onsubmit 事件发生时执行的表达式
    ng-switch	    规定显示或隐藏子元素的条件
    ng-transclude	规定填充的目标位置
    ng-value	    规定 input 元素的值
