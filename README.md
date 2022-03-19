# 精灵按钮 / SaohimeYue Button

### 参与完善本项目

- 本人暂时对**JavaScript**、**Vue**等本项目涉及的语言或框架了解不多，代码层面的改动请做充分测试后再在本项目中发起**Pull Request**

### 添加或修改音频/完善翻译

音频文件推荐使用**mp3**格式，请先音量标准化（本人用的是**MP3Gain**），然后放入`public/voices/`目录

所有的分类和音频信息都存储在`setting/translate`目录的`json`文件中，**添加或修改音频信息**、**完善翻译**，你需要修改对应文件中的内容

`locales.json`和`category.json`分别为 UI 界面翻译和分类信息，请不要修改文件名，语音信息可以使用除此外的任意名称，可使用多个`json`文件方便管理语音

可使用`schema`文件夹中的`json`文件增加`json schema`约束和代码提醒

`category.json`结构示例如下：

```jsonc
[
  {
    // 分类命名
    "name": "设定",
    // 是否隐藏
    "hide": true,
    "translate": {
      // 分类中文翻译
      "zh-CN": "设定持续追加中~",
      // 分类英文翻译
      "en-US": "Settingssssss~"
    }
  }
]
```

语音文件结构示例如下：

```jsonc
[
  {
    // 语音命名
    "name": "自我介绍（中文版）",
    // 语音文件名
    "path": "自我介绍（中文版）.mp3",
    // 是否隐藏
    "hide": true,
    "translate": {
      // 语音中文翻译
      "zh-CN": "自我介绍（中文版）",
      // 语音英语翻译
      "en-US": "Introduction(CN)"
    },
    // 语音所属分类(对应category的name)
    "category": "设定",
    // 以下属性为可选
    // hover时显示图片，请放到public/voices/img目录
    "usePicture": {
      "zh-CN": "",
      "en-US": ""
    },
    // 添加时间
    "date": "2020-11-11",
    // 语音出处
    "mark": {
      "title": "【2-19首播】我出生了！！【佐保姬夕映-WACTOR】",
      "time": "0:11:30~0:11:43",
      "url": "https://www.bilibili.com/video/BV14S4y1F7n3"
    }
  }
]
```

### 开发相关

- 本项目使用`Vue3.0`进行开发，是一个静态网页，项目内使用`yarn`进行包管理，**JavaScript**是编程语言

- 要部署本地开发环境，请先安装较新版的`Nodejs`，运行`npm install --global yarn`安装`yarn`，视需要可能要配置系统环境变量

- 以下步骤需要在命令行运行，安装**VSCode**可便于调试

- 常规流程如下：

    - **Fork**并**Clone**代码到本地
    - 进入代码目录，运行`yarn`以安装依赖项目
    - 开启本地开发服务器，运行`yarn serve`，这将会在`localhost:8080`启动，在代码或其他文件修改过程中，本地开发服务器可以即时反映修改的结果，并自动检查`json`中相关文件的使用情况
    - 增删改按钮在上述`json`文件中增删改相应项即可，不涉及**JavaScript**代码改动（所以说感谢原作者）
    - 要编译可供部署的文件，请运行`yarn build`，这将会在`dist`目录下生成可以直接部署到静态网站托管(GitHub Pages等)或服务器的文件
    - GitHub Pages的部署可参考[这个链接](https://cli.vuejs.org/zh/guide/deployment.html#github-pages)
    - 服务器要钱的（T_T）


### 计划中功能（太忙就鸽了）

- 按钮logo改动：猫耳朵-->精灵耳朵（应该涉及css文件修改，暂时是知识盲区）

- 音频补充（补录播记时间戳比较耗时）

- 部署到XX云服务器


### 使用模板

若想使用网站模板开发新的语音按钮，可以选择以下两种方式:

- 使用模板[模板项目](https://github.com/blacktunes/voices-button)修改
  - 修改`public`和`setting`目录下的文件以及`package.json`
- 使用[voices-button-cli](https://github.com/blacktunes/voices-button-cli)命令行工具生成项目

> 因为本项目含有非通用的代码以及访问统计，所以不推荐直接修改本仓库，若依然要使用，请注意：
>
> - 修改或删除**setting/setting.json**里用于访问统计的**GA_ID**

### LICENSE
- 使用[voices-button-cli](https://github.com/blacktunes/voices-button-cli)创建的语音按钮
- 所用模板为[Hiiro按钮](https://github.com/blacktunes/hiiro-button)