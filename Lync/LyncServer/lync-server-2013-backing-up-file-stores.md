---
title: ファイル ストアのバックアップ
TOCTitle: ファイル ストアのバックアップ
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202167(v=OCS.15)
ms:contentKeyID: 52056547
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ファイル ストアのバックアップ

 

_**トピックの最終更新日:** 2013-02-17_

Lync Server のファイル ストアのバックアップには、Lync Server のコンポーネントによって使用されるすべてのファイルとフォルダーが含まれます。

## ファイル ストアをバックアップするには

1.  Lync Server ファイル ストアの特定の場所を検索するには、トポロジ ビルダーを開き、\[**ファイル ストア**\] ノードを調べます。

2.  Robocopy または別のファイル システム管理ツールを使用して、各ファイル ストアを $Backup\\filestore にコピーします。

