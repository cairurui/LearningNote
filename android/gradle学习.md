### 1、AS中通过插件使用gradle
  一般需要声明插件版本
  ```
  classpath 'com.android.tools.build:gradle:2.1.2'   
  ```
### 2、项目中的gradle文件配置：
* 声明当前module类型

    apply plugin: 'com.android.application'// 声明为android应用    
    apply plugin: 'com.android.library' // 声明为library
* dependencies 节点
```
dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    compile 'com.android.support:appcompat-v7:22.2.1'
    compile 'com.facebook.fresco:fresco:0.8.1'
    compile 'com.facebook.fresco:imagepipeline-okhttp:0.8.1'
    compile project(':iapppay_res')
}
```
  * 编译libs目录下的所有jar包：compile fileTree(dir: 'libs', include: ['*.jar'])
  * 编译library：compile project(':iapppay_res')
