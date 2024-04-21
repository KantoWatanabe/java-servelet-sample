# Tomcatのインストール(Mac)

```
brew search tomcat
brew install tomcat@9
brew services start tomcat@9
```

# WARの作成とデプロイ

```
javac -classpath lib/servlet-api.jar -d WebContent/WEB-INF/classes src/sample/servlet1/SampleServlet.java src/sample/SampleServlet2.java
jar cvf sample.war -C WebContent .
cp sample.war /opt/homebrew/Cellar/tomcat@9/9.0.88/libexec/webapps
brew services restart tomcat@9
```

クラスパスが複数ある場合は以下のように指定する

```
-classpath lib/xxx.jar:lib/yyy.jar:lib/zzz.jar
```

サードパーティーのJARをTomcatにデプロイする際は以下に配置してクラスパスを通す

```
/opt/homebrew/Cellar/tomcat@9/9.0.88/libexec/lib
```
