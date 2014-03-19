---
layout: post
title: "SharedPreference"
date: 2014-03-19 07:11:43 +0800
comments: true
categories: ["公告","android"]
---

关于软件配置信息保存：
windows软件通常使用ini文件进行保存
j2se应用使用properties属性文件保存
android使用sharedpreferences方式保存

SharedPreferences，一个轻量级的存储类，适合对配置信息保存。使用SharedPreferences保存数据，其背后使用的是xml文件存放数据。
文件存放在/data/data/<package name>/shared_prefs目录下：
SharedPreferences sp = getSharedPreferences("loginInfo", Context.MODE_PRIVATE);
Editor editor = sp.edit();//获取编辑器
editor.putString("name", "");
editor.putInt("age", 4);
editor.commit();//提交修改
生成的itcast.xml文件内容如下：
<?xml version='1.0' encoding='utf-8' standalone='yes' ?>
<map>
<string name="name">传智播客</string>
<int name="age" value="4" />
</map>