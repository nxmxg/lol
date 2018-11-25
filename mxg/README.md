1.安装
  vue工具：
    3.x：npm install -g @vue/cli
    2.x：npm install -g @vue/cli-init
      安装命令：vue init webpack projectname

2.Atom安装插件
  1.快捷安装
    packages->settings View -> install package/themes
  2.命令安装(默认安装了git和node)
    cd ~/.atom/packages
    https://atom.io/packages:搜索对应插件
    https://atom.io/packages/atom-vue vue高亮插件
    https://github.com/code4mk/atom-vue 资源库
    git bash here:git clone https://github.com/code4mk/atom-vue.git
    cd atom-vue
    cnpm install

3.模板语法
  文本：
    Mustache：{{ 变量 }}：只能存在一行语句
  原始HTML
    v-html
  特性：
    v-bind:  动态绑定属性
    简约写法:v-bind: -> :
  v-once:
    只渲染一次
    通过使用 v-once 指令，你也能执行一次性地插值，当数据改变时，插值处的内容不会更新。但请留心这会影响到该节点上的其它数据绑定：

4.条件渲染
  v-if、template
  v-show
  v-if和v-show的区别：
    v-if 是“真正”的条件渲染，因为它会确保在切换过程中条件块内的事件监听器和子组件适当地被销毁和重建。
    v-if 也是惰性的：如果在初始渲染时条件为假，则什么也不做——直到条件第一次变为真时，才会开始渲染条件块。
    相比之下，v-show 就简单得多——不管初始条件是什么，元素总是会被渲染，并且只是简单地基于 CSS 进行切换。
    一般来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好。

5.列表渲染
  v-for
  参数:遍历数组：2个参数 item,index
       遍历对象：3个参数 value,key,index
  注意：在使用列表渲染的时候，要添加key作为唯一索引

6.事件处理
  methods
  v-on
  事件处理方法
  内联处理器中的方法
  事件修饰符
  简约写法:v-on: -> @

7.数组更新检测
  变异方法：
    push
    pop()
    shift()
    unshift()
    splice()
    sort()
    reverse()
  替换数组：
    filter()
    concat()
    slice()

8.计算属性侦听器
  computed
  计算属性和methods的区别
    计算属性是基于它们的依赖进行缓存的。只在相关依赖发生改变时它们才会重新求值。这就意味着只要 message 还没有发生改变，多次访问 reversedMessage 计算属性会立即返回之前的计算结果，而不必再次执行函数。
  watch

9.style与class绑定
  1.接受对象
    { active:isActive }
  2.接受数组
  3.嵌套使用
    数组嵌套对象
  4.绑定内联样式
  5.自动添加前缀

10.表单输入控件
  v-model:input textarea select
  修饰符
    .lazy
    .number
    .trim

11.组件
  1.单文件组件
    1.只能存在一个跟组件
    2.scoped:作用域
  2.组件交互
    1.父传子:props
    2.子传父:自定义事件
