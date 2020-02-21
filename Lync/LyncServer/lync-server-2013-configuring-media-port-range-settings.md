---
title: 'Lync Server 2013: メディアポート範囲設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f345b97851aac264bb3b7ef05978d80d851099ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Lync Server 2013 でのメディアポート範囲設定の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

メディア ポート範囲の設定はクライアントのパフォーマンスに大きな影響を与える可能性があるため、構成が必要です。 これらの設定は、Lync Server 管理シェルを使用して構成できます。

### <a name="media-port-range-settings"></a>メディア ポート範囲の設定

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
<th>Lync Server 管理シェルコマンドレット</th>
<th>コマンドレット パラメーター</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\ Enabled</p></td>
<td><p>サーバーから送信されたポート範囲が、クライアントでメディアと信号に使用される必要があるかどうかを指定します。 サブ値 MinMediaPort および MaxMediaPort と併用されます。</p></td>
<td><p><strong>Get-csconferencingconfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>メディアに使用する開始ポート番号を指定します。 MaxMediaPort と組み合わせて、ポート範囲を指定します。 推奨最小範囲は 40 ポートです。</p></td>
<td><p><strong>Get-csconferencingconfiguration</strong></p></td>
<td><p>ClientMediaPort (クライアントのメディアに使用する開始ポート番号を表します。)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>メディアに使用する最大ポート番号を指定します。 MinMediaPort と組み合わせて、ポート範囲を指定します。推奨最小範囲は 40 ポートです。</p></td>
<td><p><strong>Get-csconferencingconfiguration</strong></p></td>
<td><p>ClientMediaPortRange (クライアントのメディアに使用できるポートの合計数を示します。既定値は 40 です。)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>メディア ポート範囲の設定を構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のコマンドレットを実行します。
    
        Get-CsConferencingConfiguration
    
    このコマンドレットを実行すると、会議構成設定が戻されます。

3.  変更するパラメーターと値を指定して、次のコマンドレットを実行します (このコマンドレットのパラメーターの詳細については、「Lync Server Management Shell」のドキュメントを参照してください)。
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 特定サイトの会議構成設定の追加セットを作成できます。 サイト ID と共に <STRONG>New- CsConferencingConfiguration</STRONG> コマンドレットを使用します。 サイトの新しい会議構成設定を作成すると、このサイト設定はグローバル設定よりも優先されます。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

