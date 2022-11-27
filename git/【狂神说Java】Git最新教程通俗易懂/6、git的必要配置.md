[6、git的必要配置](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd)
# 一、配置语句
## （一）查看全部配置
[00:19](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=19.560949)

```bash
git config -l
```

查看当前项目下关于git的全部配置，`-l`代表list。
## （二）查看系统配置
[00:44](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=44.486219)

```bash
git config --system --list
```

查看当前项目git系统全部配置。
## （三）清除命令记录
[01:06](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=66.19077)

`clear`清理前面的命令记录。
## （四）查看全局配置
[01:09](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=69.622245)

```bash
git config --global --list
```

查看全局配置，即用户自己配置的用户名及密码，用户名及密码必须要配置，向git服务器表明你是谁。
## （五）配置用户名以及邮箱
[02:09](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=129.935202)

```bash
git config --global user.name "你设置的用户名"
git config --global user.email xxxx@xx.com
```
# 二、本地配置文件
所有的配置文件其实都保存在本地。
## (一)系统配置
[02:35](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=155.933542)

`Git\etc\gitconflig`：Git安装目录下的gitconfig [[git/【狂神说Java】Git最新教程通俗易懂/6、git的必要配置#（二）查看系统配置|--system 系统级]]
## （二）用户配置
[05:25](https://www.bilibili.com/video/BV1FE411P7B3?p=6&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=325.266393)

`C:Users\Administrator\.gitconfig` 只适用于当前登录用户的配置 [[git/【狂神说Java】Git最新教程通俗易懂/6、git的必要配置#（四）查看全局配置|--global 全局]]，如果删除了，就[[git/【狂神说Java】Git最新教程通俗易懂/6、git的必要配置#（五）配置用户名以及邮箱|这样重新配置]]。