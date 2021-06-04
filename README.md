# 🎨 PPTist
> 一个基于 Vue3.x + TypeScript 的在线演示文稿应用，还原了大部分PPT常用功能，支持 文字、图片、形状、线条、图表、表格 6种最常用的元素类型，每一种元素都拥有高度可编辑能力，同时支持丰富的快捷键和右键菜单，尽可能还原本地桌面应用的使用体验。

在线体验地址：[https://pipipi-pikachu.github.io/PPTist/](https://pipipi-pikachu.github.io/PPTist/)

如果网络状态不佳，可以访问国内镜像：[https://pptist.gitee.io/](https://pptist.gitee.io/)

Github仓库：[https://github.com/pipipi-pikachu/PPTist](https://github.com/pipipi-pikachu/PPTist)


# 🚀 项目运行
```
npm install

npm run serve
```


# 📚 功能列表
### 通用功能
- 历史记录（撤销、重做）
- 快捷键
- 右键菜单
### 幻灯片页面编辑
- 页面添加、删除
- 页面顺序调整
- 页面复制粘贴
- 背景设置（纯色、渐变、图片）
- 网格线
- 画布缩放
- 主题设置
- 幻灯片备注
### 幻灯片元素编辑
- 元素添加、删除
- 元素复制粘贴
- 元素拖拽移动
- 元素旋转
- 元素缩放
- 元素多选（框选、点选）
- 多元素组合
- 元素锁定
- 元素吸附对齐（移动和缩放）
- 元素层级调整
- 元素对齐到画布
- 元素对齐到其他元素
- 多元素均匀分布
- 拖拽添加图文
- 粘贴外部图片
- 元素坐标、尺寸和旋转角度设置
#### 文字
- 富文本编辑（颜色、高亮、字体、字号、加粗、斜体、下划线、删除线、角标、行内代码、引用、对齐方式、项目符号、清除格式）
- 行高
- 字间距
- 填充色
- 边框
- 阴影
- 透明度
#### 图片
- 裁剪（自定义、按形状、按纵横比）
- 滤镜
- 翻转
- 边框
- 阴影
- 替换图片
- 重置图片
- 设置为背景图
#### 形状
- 填充色
- 边框
- 阴影
- 透明度
- 翻转
#### 线条
- 颜色
- 宽度
- 样式
- 端点样式
#### 图表（柱状图、折线图、饼图）
- 数据编辑
- 背景填充
- 主题色
- 坐标系与坐标文字颜色
- 其他设置（柱状图转条形图、折线图转面积图、折线图转散点图、饼图转环形图、折线图开关平滑曲线）
- 边框
#### 表格
- 行、列添加删除
- 行列数设置
- 主题设置（主题色、表头、汇总行、第一列、最后一列）
- 合并单元格
- 单元格样式（填充色、文字颜色、加粗、斜体、下划线、删除线、对齐方式）
- 边框
### 幻灯片放映
- 翻页动画
- 元素入场动画
- 全部幻灯片预览
- 画笔工具


# 💡 常见问题
**Q. 为什么xxx快捷键没有作用？**

A. 部分快捷键需要聚焦到指定区域才会生效，例如焦点在左边缩略图列表才能使用操作页面的快捷键，焦点在画布区域才能使用操作元素的快捷键。

**Q. 为什么粘贴没有作用？**

A. 请注意允许浏览器访问系统剪贴板。

**Q. 为什么浏览器刷新或重新打开后，之前做的PPT没有了？**

A. 该演示项目是纯前端部署的，不会保存数据。

**Q. 如何调整幻灯片页面的顺序？**

A. 按住左侧缩略图可进行拖拽调整顺序。

**Q. 为什么插入图片后会出现操作卡顿的情况？**

A. 由于本演示项目不依赖后端，插入本地图片实际引用的是Base64，导致数据体积非常大，在真正的生产环境中应该上传图片后引用图片地址，就不会出现这样的情况了。

**Q. 为什么应用预置主题后没有效果？**

A. 设置预置主题的作用是使新添加的元素和页面应用主题样式，不会对已有的元素和页面生效，您可以使用“应用主题到全部”功能，将当前主题应用到全部页面中。

**Q. 设置在线字体不生效？**

A. 设置在线字体时会下载对应的字体文件，该文件较大，需要等待下载完成后才会应用新的字体。


# 📁 项目目录结构
```
├── assets                        // 静态资源
│   ├── fonts                     // 在线字体文件
│   └── styles                    // 样式
│       ├── antd.scss             // antd默认样式覆盖
│       ├── font.scss             // 在线字体定义
│       ├── global.scss           // 通用全局样式
│       ├── mixin.scss            // scss全局混入
│       ├── variable.scss         // scss全局变量
│       └── prosemirror.scss      // ProseMirror 富文本默认样式
├── components                    // 与业务逻辑无关的通用组件
├── configs                       // 配置文件，如：画布尺寸、字体、动画配置、快捷键配置、预置形状、预置线条等数据。
├── hooks                         // 供多个组件（模块）使用的 hooks 方法
├── mocks                         // mocks 数据
├── plugins                       // 自定义的 Vue 插件
├── types                         // 类型定义文件
├── store                         // Vuex store，参考：https://vuex.vuejs.org/zh/guide/
├── utils                         // 通用的工具方法
└── views                         // 业务组件目录，分为 `编辑器` 和 `播放器` 两个部分。
    ├── components                // 公用的业务组件
    ├── Editor                    // 编辑器模块
    └── Screen                    // 播放器模块
```


# 💿 数据
幻灯片的数据主要由 `slides` 和 `theme` 两部分组成。
> 换句话说，在实际的生产环境中，一般只需要存储这两项数据即可。

- `slides` 表示幻灯片页面数据，包括每一页的ID、元素内容、备注、背景、动画、切页方式等信息
- `theme` 表示幻灯片主题数据，包括背景色、主题色、字体颜色、字体等信息

具体类型的定义可见：[https://github.com/pipipi-pikachu/PPTist/blob/master/src/types/slides.ts](https://github.com/pipipi-pikachu/PPTist/blob/master/src/types/slides.ts)


# 📃 TODO
- [ ] 幻灯片模板
- [ ] 图表缩略图优化
- [ ] 公式元素
- [ ] 导出、导入

> 作为一个在线幻灯片，导出、导入PPTX文件是非常重要的功能。但是经过本人一段时间的调研发现，该功能实现起来的复杂度远超过了预期。由于个人时间有限，暂时可能无法集中精力来做该功能，短时间内还是会更多优先去提升其他方面的使用体验。如果有做过相关内容的朋友，也欢迎给我提建议。


# 💻 贡献代码
首先感谢每一位关注本项目的朋友，由于本人时间精力有限，且目前项目规模不大，暂时没有团队化开发维护本项目的打算。但非常欢迎每一位对本项目感兴趣的朋友贡献代码。
### 具体参考如下：
- fork 源码，下载到本地并运行项目
- 修改代码并进行自我测试后提交修改到 github
- 提交 Pull Request

### 另外需要注意的是：
- 每一次 Pull Request 都不应该提交过多的代码，且务必说明本次改动的具体目的，例如：修复了某个 bug、优化了某个方法 等，方便进行 Code Review；
- 对于 bug 的修复，应该将本次 Pull Request 和相对应 bug 的 issue 关联起来，让别人知道该问题已经被修复；
- 对于较大的新功能，你需要先提交 Issues，例如 ‘添加 XXX 功能’，确认该功能有被添加的必要后，再开始工作；
- 其他如简单的体验或代码优化、文档修正等，只要修改合理都会被接受。

在此，感谢每一位贡献者。


# 📄 开源协议
[MIT License](https://github.com/pipipi-pikachu/PPTist/blob/master/LICENSE)


# 💣 友情提示
本项目不接受任何形式的私人咨询，有任何问题 [欢迎在 github 提交你的 Issues](https://github.com/pipipi-pikachu/PPTist/issues)