## 使用方式

- 把图片移动到 `assets` 文件夹中
- 执行`git commit` & `git push` 推送你的代码到 github

github actions 检测到项目中 .github 文件夹下的部署脚本之后，将会启动自动化构建把你的图片打包编译到 gh-pages 分支上去。

如果你发现生成的图片链接可以访问，但是放在 github 的 readme.md 中无法显示，那最有可能是 `githubusercontent.com` 被本地服务商 DNS 污染，解决方案是加入如下 DNS 解析到你的 hosts 文件中：

```
199.232.96.133 raw.githubusercontent.com
199.232.96.133 camo.githubusercontent.com
```

如果你发现访问 github 很慢，那是因为本地服务商在进行 DNS 网络过滤，加入如下 host 跳过服务商网络过滤：

```
140.82.112.3 github.com
```

## 配置文件

```json
{
  // 支持的图片格式
  "types": ["svg", "png", "jpg", "jpeg", "gif", "webp"],

  // 开启图片压缩，当compress : false时，关闭压缩
  // 仅支持对jpg、png、gif进行压缩
  "compress": {
    // 图片质量 0.1 - 1
    "quality": 0.8,
    // 如果设定为true，webp，jpg、png将使用imagemin的webp插件进行压缩
    "webp": false
  },

  // 文件夹读取深度
  "depth": 12
}
```
