# 图片管理、雪碧图生成

1. 执行 node ./ ./images， 生成雪碧图
2. 将 dist/sprite.png 上传至 CDN
3. 修改 src/assets/styles/iconmap.scss 中 \$iconMap 图片地址
4. 将 dist/sprite-css.txt 内容复制到 src/assets/styles/iconmap.scss 中，进行使用

## 使用

### scss 写法

```
// iconMap
$iconMap: url(xxx.png);

@mixin iconmapBaseSet($x, $y, $w, $h) {
  display: block;
  width: $w;
  height: $h;
  overflow: hidden;
  background-image: $iconMap;
  background-position: $x $y;
  background-size: 844rpx 438rpx;
}

.iconmap {
  &-add { @include iconmapBaseSet(-0rpx, -0rpx, 48rpx, 48rpx); }
  &-arrow_right { @include iconmapBaseSet(-48rpx, -0rpx, 32rpx, 32rpx); }
}
```

### less 写法

```
@iconMap: url(xxx.png);
.iconmapBaseSet(@x, @y, @w, @h) {
  display: block;
  width: @w;
  height: @h;
  overflow: hidden;
  background-image: @iconMap;
  background-position: @x @y;
  background-size: 469px 244px;
}

.iconmap {
  &-bttombar-home { .iconmapBaseSet(-127px, -74px, 48rpx, 48rpx); }
  &-bttombar-home--active { .iconmapBaseSet(1px, -74px, 48rpx, 48rpx); }
}
```
