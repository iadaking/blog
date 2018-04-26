[TOC]

#  java: -source 1.5 中不支持 diamond 运算符  (请使用 -source 7 或更高版本以启用 diamond 运算符)

## 解决方法

在 offer.iml 文件中寻找到 `<component name="NewModuleRootManager" LANGUAGE_LEVEL="JDK_1_5">` 将 `LANGUAGE_LEVEL="JDK_1_5"` 修改为 `LANGUAGE_LEVEL="JDK_1_8"` 

