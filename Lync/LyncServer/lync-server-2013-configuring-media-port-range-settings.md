---
title: メディア ポート範囲設定の構成
TOCTitle: メディア ポート範囲設定の構成
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48271655
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# メディア ポート範囲設定の構成

 

_**トピックの最終更新日:** 2015-03-09_

メディア ポート範囲の設定はクライアントのパフォーマンスに大きな影響を与える可能性があるため、構成が必要です。これらの設定は、Lync Server 管理シェルを使用して構成できます。

### メディア ポート範囲の設定

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>設定</th>
<th>説明</th>
<th>Lync Server 管理シェル コマンドレット</th>
<th>コマンドレット パラメーター</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>サーバーから送信されたポート範囲が、クライアントでメディアと信号に使用される必要があるかどうかを指定します。 サブ値 MinMediaPort および MaxMediaPort と併用されます。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>メディアに使用する開始ポート番号を指定します。 MaxMediaPort と組み合わせて、ポート範囲を指定します。 推奨最小範囲は 40 ポートです。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (クライアントのメディアに使用する開始ポート番号を表します。)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>メディアに使用する最大ポート番号を指定します。 MinMediaPort と組み合わせて、ポート範囲を指定します。推奨最小範囲は 40 ポートです。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (クライアントのメディアに使用できるポートの合計数を示します。既定値は 40 です。)</p></td>
</tr>
</tbody>
</table>


## メディア ポート範囲の設定を構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドレットを実行します。
    
        Get-CsConferencingConfiguration
    
    このコマンドレットを実行すると、会議構成設定が戻されます。

3.  変更するパラメーターおよび値を指定して、次のコマンドレットを実行します (このコマンドレットのパラメーターの詳細については、Lync Server 管理シェルのドキュメントを参照してください)。
    
        Set-CsConferencingConfiguration
    
    > [!NOTE]
    > 特定サイトの会議構成設定の追加セットを作成できます。 サイト ID と共に <strong>New- CsConferencingConfiguration</strong> コマンドレットを使用します。 サイトの新しい会議構成設定を作成すると、このサイト設定はグローバル設定よりも優先されます。詳細については、Lync Server 管理シェルのドキュメントを参照してください。

