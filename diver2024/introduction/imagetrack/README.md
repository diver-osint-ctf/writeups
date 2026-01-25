---
title: imagetrack
description: 
author: k4r45u
genre: introduction
solver: 0 
point: 0
---

# imagetrack

## 問題文
    画像の撮影された郷土料理屋の店名を答えよ。
    Flagは `Diver24{店名}` です。

## 難易度
    easy

## 解法
    画像情報をexiftoolで解析して画像に含まれている座標情報をGoogleMapで調べる。