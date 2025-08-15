# Others

###RubyGems 换源

```
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
gem sources -l
```

### Bundler换源

```
bundle config mirror.https://rubygems.org https://gems.ruby-china.com
```

### Error: No source of timezone data could be found

检查gemfile文件，看是否存在tzinfo-data, 若已经存在，会找到类似以下的一行，

```
gem 'tzinfo-data', platforms: [:mingw, :mswin]
```

由于使用的64位的系统，因此需要给platforms增加:x64_mingw的设置，即：

```
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw]
```

### 在启动服务器的过程中提示错误 cannot load such file -- webrick (LoadError)

执行命令添加 webrick

```text
bundle add webrick
```

### “ No source of timezone data could be found. (TZInfo::DataSourceNotFound) #8 ”

删除Gemfile.lock文件，然后，在Gemfile文件中，加入两个安装依赖。

```text
gem 'tzinfo'
gem 'tzinfo-data'
```

如果在Windwos上使用的MinGW这种系统，还可以加入后缀修饰，指定平台信息。

```text
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw] 
```

bundle

```
bundle clean
bundle update
bundle install
bundle lock --add-platform x86_64-linux
bundle exec jekyll serve
```
git

```
git add .
git commit -m "commit"
% git pull
git push
```

