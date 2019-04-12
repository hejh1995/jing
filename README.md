# jing微信小程序开发实战。
## 组件化开发
## 主要实现的功能：
- 请求的封装：封装一个类具有request方法，内部调用wx.request方法，返回一个promise，可以避免回调地狱。
- models 文件夹中，API的封装。
- 组件： 喜欢组件，页面组件，加载信息组件，
- 页面切换。如果是音乐页面，在组件的attached阶段，判断音乐是否播放，旋转背景，更换图标。
- 音乐播放：wx.getBackgroundAudioManager()，调取微信背景音乐播放，有onplay，onpause，onstop，onended方法。
- 
## 页面功能：
- 期刊切换。类似分页加载数据吧，点击切换的时候，判断是不是特殊情况（第一个不能再向前了，最后一个不能再向后了），如果不是就获取数据。
- 标记是否喜欢当前的期刊。（期刊加载的时候也要去获取是否喜欢）
- 搜索的上拉加载。onReachBottom函数中，改变参数，组件中监听到变化，调用observer函数，采用了加锁的方式，在加载数据或没有更多数据的时候return，在加载数据前加锁，加载数据后解锁（失败也要解锁）。
- 搜索历史的保存。使用wx.setStorageSync(key, value),wx.getStorageSync(key)。
## 和vue很像的不同：
- 父子组件间通信，properties的属性，会有一个observer方法，当参数发生变化的时候会被触发。
- 
## 页面展示：
![image](https://github.com/hejh1995/project-img/blob/master/picture/1.png)
![image](https://github.com/hejh1995/project-img/blob/master/picture/2.png)
![image](https://github.com/hejh1995/project-img/blob/master/picture/3.png)
![image](https://github.com/hejh1995/project-img/blob/master/picture/4.jpg)
![image](https://github.com/hejh1995/project-img/blob/master/picture/5.png)
![image](https://github.com/hejh1995/project-img/blob/master/picture/6.jpg)

