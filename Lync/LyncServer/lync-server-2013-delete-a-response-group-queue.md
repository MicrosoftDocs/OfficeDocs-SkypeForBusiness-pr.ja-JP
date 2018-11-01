---
title: 応答グループのキューの削除
TOCTitle: 応答グループのキューの削除
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48272362
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 応答グループのキューの削除

 

_**トピックの最終更新日:** 2012-11-01_

キューを削除するには、次のいずれかの方法を使用します。

## Lync Server コントロール パネルを使用してキューを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**応答グループ**\] をクリックし、\[**キュー**\] をクリックします。

4.  検索フィールドで、削除するキューの名前の一部または全部を入力します。

5.  キューの一覧で対象のキューをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## コマンドレットを使用してキューを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    次に例を示します。
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

