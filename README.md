

# litepaltest
*   使用LitePal操作数据库

    要使用LitePal的第一步，就是编辑app/build.gradle文件，在dependencies闭包中添加如下内容：

     compile 'org.litepal.android:core:1.3.2'
     
     这样我们就把LitePal成功引入到当前项目中了，接下来就是要配置litepal.xml文件。右击app/src/main目录下新建一个assets文件夹，然后在这个文件夹下再新建一个litepal.xml文件，接着编辑litepal.xml中的内容，如下所示：
     <?xml version="1.0" encoding="utf-8"?>
<litepal>
    <dbname value="BookStore" ></dbname>

    <version value="2" ></version>

    <list>
        <mapping class="com.example.litepaltest.Book"></mapping>
        <mapping class="com.example.litepaltest.Category"></mapping>
    </list>
</litepal>

  最后还需要配置一下LitePalApplication，修改AndroidManifest.xml中的代码，如下所示：
  <application
        android:name="org.litepal.LitePalApplication"
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
    
   
  LitePal采取的是对象关系映射（ORM）的模式，那什么是是对象关系映射呢？简单点说，我们使用的编程语言是面向对象语言。而使用的数据库则是关系型数据库，那么将面向对象的语言和面向关系的数据库建立一种映射关系，这就是对象关系映射了。 
  
  配置完这些，我们就可以用面向对象的思维来操作数据库
