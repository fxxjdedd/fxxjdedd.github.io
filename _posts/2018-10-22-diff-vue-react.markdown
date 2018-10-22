---
layout:     post
title:      "Vue和React的update优化区别"
subtitle:   "为什么优化Vue的update过程这么难?"
date:       2018-10-22 12:00:00
author:     "Tengda"
header-img: "img/post-bg-2018-10-22.jpg"
tags:
    - 技术
---

# 前言
优化页面的update过程对我来说一直是个难题，使用Vuex或者Redux的思想，的确可以让update过程变得清晰，
但只局限于让我们知道数据是怎么引起update的，对于如何update这个过程还是需要我们自己来的。

# 为什么优化Vue的update过程这么难?
总的来说就是，Vue压根就不给外界暴露出能控制update过程的勾子函数。我们知道Vue的特色是双向绑定，它很智能，
以至于它包揽了数据变化之后的所有工作(什么时候update应不应该update)，这都是Vue说的算。这样做的好处很明显，
用户不需要关注update的细节，可以快速开发产品，但是坏处也很明显，用户无法控制update的过程，除非...你透彻地
理解了Vue的响应式原理。

相对来说，React虽然没有Vue"智能"，但使用户能够根据自己的意愿来手动控制update的过程。坏处呢，可能就是麻烦了点，
虽然也有pureComponent这样的组件，但跟Vue比起来，还是要多写一些"控制"的代码。

