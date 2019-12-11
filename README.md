# Obj 转 js/json

将 Obj 模型转换为 js 或 json ，适用于 Three.js ，目的为提取模型的顶点信息。

## 前言

Three.js 在 R94 版本移除了该转换器。取而代之的 `obj2three.js` 转换器使用更加方便，但提取顶点的时候因为没有去除 WebGL 绘制的重复点，导致顶点数量翻倍，对于制作粒子效果来说，性能也就随着粒子数量的增加而减弱了，因此旧的 `convert_obj_three` 转换器在提取顶点信息的时候还是很有必要的。

## 配置环境
### Python 安装
`convert_obj_three` 转换器使用的是 python 环境，而且只支持旧版本的 python，推荐使用 [python 2.7.1](https://www.python.org/downloads/release/python-2711/)。

### 配置环境变量

1. 右键点击"计算机"，然后点击"属性"；
2. 然后点击"高级系统设置"；
3. 选择"系统变量"窗口下面的"Path"；
4. 然后在"Path"行，添加python安装路径即可(如的C:\Python27)；
5. 设置成功以后，在命令行输入命令"python"，有版本号则说明配置完成了。

## 开始转换

1. 保存 [convert_obj_three.py](./convert_obj_three.py) 文件到本地；
2. 打开命令行，切换到该目录下；
3. 将 obj 文件复制到该文件夹内；
3. 使用命令完成转换。

```git
python convert_obj_three.py -i model.obj -o model.js
```

## 总结

- `model.obj` 为输入文件
- `model.js` 为输出文件，可以转为 `json` 文件
- `model.js` 文件中的 `vertices` 属性即为模型的全部顶点信息
