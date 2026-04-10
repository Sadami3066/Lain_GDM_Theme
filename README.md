Optimizing tool selection...开始检查当前 README.md 内容。

Read [](file:///home/whywood/project/gdmtheme/README.md)

# GDM 主题

可爱的lain的登录主题。

!preview

## 安装

### 方法一：直接替换（预编译）

1. 从本项目下载 gnome-shell-theme.gresource

2. 找到当前使用的主题目录（以 Ubuntu 25.10 Yaru 主题为例）：

   ```bash
   sudo cp gnome-shell-theme.gresource /usr/share/gnome-shell/theme/Yaru/
   ```

3. 重启以应用更改

> **⚠️ 警告**：这会覆盖原系统主题。建议先备份原文件，或在安全环境中测试。
>
> ```bash
> # 备份原文件（需 root）
> sudo cp /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource.backup
> ```

### 方法二：克隆并替换

```bash
# 克隆项目
git clone https://github.com/your-repo/gdmtheme.git
cd gdmtheme

# 替换系统主题文件
sudo cp gnome-shell-theme.gresource /usr/share/gnome-shell/theme/Yaru/
```

## 开发

如果你想定制背景图片、颜色或其他样式，可以修改 CSS 并重新编译主题。

### 第一步：修改样式

编辑 gdm.css，可定制：

- 背景图片：`background-image: url('lain.jpg');`
- 颜色：`color: #ffffff;`
- 边框圆角：`border-radius: 16px;`

> 你可以将修改需求发送给 AI 助手，来帮助调整 CSS。

### 第二步：编译主题

修改 CSS 后，将所有资源文件编译成 `.gresource` 文件：

```bash
# 进入项目目录
cd gdmtheme

# 使用 gresource 编译主题
glib-compile-resources --target=gnome-shell-theme.gresource --sourcedir=. gnome-shell-theme.gresource.xml
```

### 第三步：替换文件

编译完成后，按“安装”部分的步骤替换系统主题文件。

### 备份与恢复

要恢复原主题：

```bash
sudo cp /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource.backup /usr/share/gnome-shell/theme/Yaru/gnome-shell-theme.gresource
```

## 文件说明

| 文件 | 说明 |
|------|------|
| gnome-shell-theme.gresource | 已编译的主题资源文件 |
| gnome-shell-theme.gresource.xml | 资源清单（用于编译） |
| gdm.css | GDM 登录界面样式 |
| gnome-shell-dark.css | 暗色主题样式 |
| gnome-shell-light.css | 亮色主题样式 |
| lain.jpg | 背景图片 |