A Github Pages template for academic websites. This was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License. See LICENSE.md.

I think I've got things running smoothly and fixed some major bugs, but feel free to file issues or make pull requests if you want to improve the generic template / theme.

### Note: if you are using this repo and now get a notification about a security vulnerability, delete the Gemfile.lock file. 

# Instructions

1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section
1. (Optional) Use the Jupyter notebooks or python scripts in the `markdown_generator` folder to generate markdown files for publications and talks from a TSV file.

See more info at [https://academicpages.github.io/](https://academicpages.github.io/)

## To run locally (not on GitHub Pages, to serve on your own computer)

1. Clone the repository and made updates as detailed above
1. Make sure you have ruby-dev, bundler, and nodejs installed: `sudo apt install ruby-dev ruby-bundler nodejs`
1. Run `bundle clean` to clean up the directory (no need to run `--force`)
1. Run `bundle install` to install ruby dependencies. If you get errors, delete Gemfile.lock and try again.
1. Run `bundle exec jekyll liveserve` to generate the HTML and serve it from `localhost:4000` the local server will automatically rebuild and refresh the pages on change.

# Changelog -- bugfixes and enhancements

There is one logistical issue with a ready-to-fork template theme like academic pages that makes it a little tricky to get bug fixes and updates to the core theme. If you fork this repository, customize it, then pull again, you'll probably get merge conflicts. If you want to save your various .yml configuration files and markdown files, you can delete the repository and fork it again. Or you can manually patch. 

To support this, all changes to the underlying code appear as a closed issue with the tag 'code change' -- get the list [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aclosed%20is%3Aissue%20label%3A%22code%20change%22%20). Each issue thread includes a comment linking to the single commit or a diff across multiple commits, so those with forked repositories can easily identify what they need to patch.



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

Hint1
```
bundle clean
bundle update
bundle install
bundle lock --add-platform x86_64-linux
bundle exec jekyll serve
```
Hint2
```
git add .
git commit -m "commit"
% git pull
git push
```

