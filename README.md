# baidu-translate
An emacs plugin using baidu-translate-api

## 依赖
本插件需要unicode-escape插件的支持 <br>
你可以通过package-list-packages安装<br>
也可以去 https://github.com/kosh04/unicode-escape.el 下载<br>

## 安装方法
将baidu-translate.el 下载到.emacs.d文件夹下<br>
在.emacs 中添加<br>
```elisp
(require 'baidu-translate)
;;设置快捷键
(global-set-key (kbd "C-c m") 'baidu-translate-zh-mark)
(global-set-key (kbd "C-c M") 'baidu-translate-zh-whole-buffer)
```
申请百度翻译API，在.emacs中填写APPID和秘钥。<br>
```elisp
;;需要去百度申请API
;;设置你的百度翻译APPID
(setq baidu-translate-appid "your APPID")
;;设置你的秘钥
(setq baidu-translate-security "your SECURITY")
```

## 翻译为其他语言
你可以通过源代码中的例子，查看百度翻译的语言列表，通过对baidu-translate-string 函数的包装，编写自己的UI函数，并设置快捷键。<br>
例如：<br>
```elisp
(defun baidu-translate-zh-mark (start end)
  "Translate the marked text to Chinese."
  (interactive "r")
  (baidu-translate-string (buffer-substring start end) "auto" "zh"))

(defun baidu-translate-zh-whole-buffer ()
  "Translate the whole buffer to Chinese."
  (interactive)
  (baidu-translate-string (buffer-string) "auto" "zh"))
```
## 效果图
![Preview](preview.jpg)
