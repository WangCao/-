# useEffect 使用技巧

最近在使用 hook 的时候用到 useEffect，有很多东西需要记录：

## 相关文章

[useEffect 完整指南](https://overreacted.io/zh-hans/a-complete-guide-to-useeffect/)

而是 effect 函数本身在每一次渲染中都不相同。

组件内的每一个函数（包括事件处理函数，effects，定时器或者 API 调用等等）会捕获定义它们的那次渲染中的 props 和 state。

“但我只是想在挂载的时候运行它！”，你可能会说。现在只需要记住：如果你设置了依赖项，effect 中用到的所有组件内的值都要包含在依赖中。这包括 props，state，函数 — 组件内的任何东西。

当你写类似 setSomething(something => ...)这种代码的时候，也许就是考虑使用 reducer 的契机。reducer 可以让你把组件内发生了什么(actions)和状态如何响应并更新分开表述。

如果一个函数没有使用组件内的任何值，你应该把它提到组件外面去定义，然后就可以自由地在 effects 中使用

useCallback 本质上是添加了一层依赖检查。它以另一种方式解决了问题 - 我们使函数本身只在需要的时候才改变，而不是去掉对函数的依赖。
