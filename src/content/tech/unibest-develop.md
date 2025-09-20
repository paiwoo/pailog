---
title: "🚀  unibest 模板 快速修改"
tags: [tech]
draft: false
weight: 9
---

# unibest 模板 → 青草地健康中心 快速改完清单

> 自用对照表，按顺序打钩即可上线

- [ ] 1. 解除提交钩子

  ```bash
  rm -rf .husky
  ```

- [ ] 2. 全局标题  
     `src/pages.config.ts`

  ```ts
  defineUniPages({
    navigationBarTitleText: "青草地健康中心",
  });
  ```

- [ ] 3. TabBar 图标 & 文字  
     文件：`src/tabbar/config.ts`

  3-1 补 icon 白名单  
  `unocss.config.ts`

  ```ts
  safelist: [
    "i-carbon-code",
    "i-carbon-home",
    "i-carbon-user",
    "i-carbon-wallet",
    "i-carbon-grid", // ← 新增
  ];
  ```

  3-2 替换列表

  ```ts
  export const customTabbarList: CustomTabBarItem[] = [
    {
      text: "",
      pagePath: "pages/ppw/index/index",
      iconType: "unocss",
      icon: "i-carbon-home",
    },
    {
      text: "",
      pagePath: "pages/ppw/svc/list/index",
      iconType: "unocss",
      icon: "i-carbon-grid",
    },
    {
      text: "卡包",
      pagePath: "pages/ppw/card/list/index",
      iconType: "unocss",
      icon: "i-carbon-wallet",
    },
    {
      text: "我的",
      pagePath: "pages/ppw/me/index",
      iconType: "unocss",
      icon: "i-carbon-user",
    },
  ];
  ```

- [ ] 4. 业务目录  
     `src/pages/ppw/` ← 所有页面扔这里，路由自动扫描
