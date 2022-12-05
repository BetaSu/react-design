## 《React 设计原理》纸质书全部示例

注：所有示例使用各框架的官方`repl`或者`codesandbox`编辑，如果无法打开请考虑科学上网

### 示例 1-1

细粒度更新实现

[地址](https://codesandbox.io/s/happy-khayyam-cyfri?file=/index.html)

### 示例 1-2

`Svelte`示例的基础组件

[地址](https://svelte.dev/repl/9945d189204a4168b4c23890f1d92a3a?version=3.19.1)

### 示例 1-3

`Svelte`示例，`count`可变化的基础组件

[地址](https://svelte.dev/repl/bf22a31a0eff4875b5b3084aa2b85fc3?version=3.19.1)

### 示例 1-4

`Vue3`示例，`count`可变化的基础组件

[地址](https://sfc.vuejs.org/#eyJBcHAudnVlIjoiPHNjcmlwdCBzZXR1cD5cbmltcG9ydCB7IHJlZiB9IGZyb20gJ3Z1ZSdcbmxldCBjb3VudCA9IHJlZigwKVxuPC9zY3JpcHQ+XG5cbjx0ZW1wbGF0ZT5cbiAgPGgxIEBjbGljaz1cImNvdW50KytcIj57e2NvdW50fX08L2gxPlxuPC90ZW1wbGF0ZT4iLCJpbXBvcnQtbWFwLmpzb24iOiJ7XG4gIFwiaW1wb3J0c1wiOiB7XG4gICAgXCJ2dWVcIjogXCJodHRwczovL3NmYy52dWVqcy5vcmcvdnVlLnJ1bnRpbWUuZXNtLWJyb3dzZXIuanNcIlxuICB9XG59In0=)

### 示例 1-5

`Vue3`模版编译

[地址](https://vue-next-template-explorer.netlify.app/#%7B%22src%22%3A%22%3Cdiv%3E%5Cn%20%20%3Ch3%3Ehello%3C%2Fh3%3E%5Cn%20%20%3Cp%3E%7B%7Bname%7D%7D%3C%2Fp%3E%5Cn%3C%2Fdiv%3E%5Cn%22%2C%22options%22%3A%7B%22mode%22%3A%22module%22%2C%22filename%22%3A%22Foo.vue%22%2C%22prefixIdentifiers%22%3Afalse%2C%22hoistStatic%22%3Afalse%2C%22cacheHandlers%22%3Atrue%2C%22scopeId%22%3Anull%2C%22inline%22%3Atrue%2C%22ssrCssVars%22%3A%22%7B%20color%20%7D%22%2C%22compatConfig%22%3A%7B%22MODE%22%3A3%7D%2C%22whitespace%22%3A%22condense%22%2C%22bindingMetadata%22%3A%7B%22TestComponent%22%3A%22setup-const%22%2C%22setupRef%22%3A%22setup-ref%22%2C%22setupConst%22%3A%22setup-const%22%2C%22setupLet%22%3A%22setup-let%22%2C%22setupMaybeRef%22%3A%22setup-maybe-ref%22%2C%22setupProp%22%3A%22props%22%2C%22vMySetupDir%22%3A%22setup-const%22%7D%7D%7D)

### 示例 2-1

我们有个更新很耗时的大列表，让我们看看**同步更新**和**异步更新**时，输入框的响应速度

可以从 Demo 看到，当牺牲了列表的更新速度，`React`大幅提高了输入响应速度，使交互更自然。

[地址](https://codesandbox.io/s/concurrent-3h48s?file=/src/index.js)

### 示例 2-2

`count`默认为 0，每次点击按钮`count++`

列表中 3 个`li`的值分别为 1，2，3 乘以`count`的结果

[地址](https://codesandbox.io/s/spring-wave-3jvv6)

### 示例 2-3

`count`默认为 0，每次点击按钮`count = count + 1`，观察使用`并发特性`（useTransition）后开启的`并发更新`

[地址](https://codesandbox.io/s/react-concurrent-mode-demo-forked-z7r0j?file=/src/index.js)

### 示例 2-4

`count`默认为 0，每次点击按钮`count = count + 1`

[地址](https://codesandbox.io/s/floral-bash-2dhnb?file=/src/App.js)

### 示例 2-5

本书推荐方式和官方方式

[地址](./assets/source.md)

### 示例 3-1

运行`本书推荐方式`对应项目，使用`src/demo/RenderPhaseDemo.tsx`调试`render阶段`工作流程

### 示例 3-2

自制`ReactDOM Renderer`

[地址](https://codesandbox.io/s/quiet-feather-05gvk?file=/src/index.js)

### 示例 4-1

运行`本书推荐方式`对应项目，使用`src/demo/CommitPhaseDemo.tsx`调试`commit阶段`工作流程

### 示例 4-2

`Suspense`在新旧版本行为的区别

官方讨论见[Behavioral changes to Suspense in React 18 #7](https://github.com/reactwg/react-18/discussions/7)

改变示例中的`CREATE_ROOT`常量，打开控制台，审查元素，对比**是否开启并发更新**带来的区别

[地址](https://codesandbox.io/s/epic-sea-omumbh?file=/src/App.js)

### 示例 4-3

运行`本书推荐方式`对应项目，使用`src/demo/ErrorCatchDemo.tsx`调试`错误处理`工作流程

### 示例 5-1

`Scheduler`实现调度流程，提供两种使用方式：

1. [在线 Demo 地址](https://codesandbox.io/s/xenodochial-alex-db74g?file=/src/index.ts)

2. 运行`本书推荐方式`对应项目，使用`src/demo/MiniSchedulePhase`调试

### 示例 5-2

点击`Demo`中的`CLICK ME`，观察请求途中数字是否能继续变化

[老模型下有 bug 版本的地址](https://codesandbox.io/s/usetransition-stop-reacting-passed-props-updates-forked-5e7lh)
[新模型下没 bug 版本的地址](https://codesandbox.io/s/usetransition-stop-reacting-passed-props-updates-zoqm2?file=/src/index.js)

### 示例 5-3

即使在**未开启并发特性**时，触发更新后也无法立刻获取更新后的值

[地址](https://codesandbox.io/s/inspiring-pond-poi2o?file=/src/App.js)

### 示例 5-4

`Batched Updates`

[地址](https://codesandbox.io/s/react-concurrent-mode-demo-forked-fecyne?file=/src/index.js)

### 示例 5-5

用三款框架实现`Batched Updates`，打印结果不同：

[React](https://codesandbox.io/s/react-concurrent-mode-demo-forked-t8mil?file=/src/index.js)

[Vue3](https://codesandbox.io/s/crazy-rosalind-wqj0c?file=/src/App.vue)

[Svelte](https://svelte.dev/repl/1e4e4e44b9ca4e0ebba98ef314cfda54?version=3.44.1)

### 示例 6-1

`事件系统`简易实现，提供 2 种使用方式：

1. [在线 Demo 地址](https://codesandbox.io/s/optimistic-torvalds-9ufc5?file=/src/index.js)

2. 运行`本书推荐方式`对应项目，使用`src/demo/MiniEventSystem`调试

### 示例 6-2

性能优化示例：[在线 Demo 地址](https://codesandbox.io/s/frosty-cerf-mg64o5?file=/src/App.js:46-318)

### 示例 6-3

`Context`面对`bailout策略`的示例：[在线 Demo 地址](https://codesandbox.io/s/crazy-morning-5keghq?file=/src/App.js)

### 示例 6-4

[应用 1](https://codesandbox.io/s/proud-wildflower-zmc02e?file=/src/App.js)

[应用 1 优化后](https://codesandbox.io/s/strange-carlos-74yl2g?file=/src/App.js)

[应用 2](https://codesandbox.io/s/recursing-cdn-sgozen?file=/src/App.js)

[应用 2 优化后](https://codesandbox.io/s/nostalgic-chatelet-yc7n2f?file=/src/App.js)

### 示例 7-1

1. [在线 Demo 地址](https://codesandbox.io/s/naughty-matan-6fq7n6?file=/src/diff.ts)

2. 运行`本书推荐方式`对应项目，使用`src/demo/MiniDiff`调试

### 示例 8-1

1. [在线 Demo 地址](https://codesandbox.io/s/little-shape-nohj59?file=/src/index.js)

2. 运行`本书推荐方式`对应项目，使用`src/demo/SuspenseDemo/demo2.tsx`调试

### 示例 8-2

1. [在线 Demo 地址](https://codesandbox.io/s/cranky-pare-rk7e0d?file=/src/index.ts:530-533)

2. 运行`本书推荐方式`对应项目，使用`src/demo/MiniUseState/index.ts`调试

### 示例 8-3

[在线 Demo 地址](https://codesandbox.io/s/admiring-violet-50dz94?file=/src/App.tsx)

### 示例 8-4

[在线 Demo 地址](https://codesandbox.io/s/sandpack-project-forked-s33q3c?file=/App.js:67-70)

### 示例 8-5

[在线 Demo 地址](https://codesandbox.io/s/sandpack-project-forked-7zqgmd?file=/App.js)

### 示例 8-6

1. [在线 Demo 地址](https://codesandbox.io/s/hidden-grass-w5qe54?file=/src/App.js:78-428)

2. 运行`本书推荐方式`对应项目，使用`src/demo/TransitionDemo/demo1.tsx`调试

### 示例 8-7

1. [在线 Demo 地址](https://codesandbox.io/s/immutable-glade-u0m6vv?file=/src/App.js)

2. 运行`本书推荐方式`对应项目，使用`src/demo/TransitionDemo/demo2.tsx`调试

### 示例 8-8

1. [在线 Demo 地址](https://codesandbox.io/s/youthful-antonelli-qnorue?file=/src/App.js:210-231)

2. 运行`本书推荐方式`对应项目，使用`src/demo/TransitionDemo/demo3.tsx`调试

### 示例 8-9

1. [在线 Demo 地址](https://codesandbox.io/s/angry-mountain-xstgj4?file=/src/App.js)

2. 运行`本书推荐方式`对应项目，切换分支到`use-error-boundary`调试，在[Comparing changes](https://github.com/BetaSu/react18-demo/compare/use-error-boundary)中查看改动的代码
