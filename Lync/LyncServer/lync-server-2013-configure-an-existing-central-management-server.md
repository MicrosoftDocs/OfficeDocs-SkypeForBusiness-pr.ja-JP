---
title: 'Lync Server 2013: 既存の中央管理サーバーの構成'
TOCTitle: 既存の中央管理サーバーの構成
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48273787
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での既存の中央管理サーバーの構成

 

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 の既存展開の中央管理サーバーを再利用する場合は、以下で説明する手順を実行して、Lync Server コントロール パネルおよび Windows PowerShell が正しく機能することを確認する必要があります。

## 既存の 中央管理サーバーを構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **Update-CsAdminRole** コマンドレットを使用して、 中央管理サーバーに格納されている役割ベースのアクセス制御 (RBAC) の役割を更新します。
    
    > [!NOTE]
    > エラーがない限り、何も出力されません。

