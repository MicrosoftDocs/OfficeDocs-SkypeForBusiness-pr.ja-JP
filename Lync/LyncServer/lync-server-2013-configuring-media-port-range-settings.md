---
title: 'Lync Server 2013: メディアポート範囲の設定を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Lync Server 2013 でメディアポート範囲設定を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

メディアポート範囲の設定は、クライアントのパフォーマンスに大きな影響を与え、構成する必要があります。 Lync Server 管理シェルを使用して、これらの設定を構成できます。

### <a name="media-port-range-settings"></a>メディアポート範囲の設定

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
<th>Lync Server Management Shell コマンドレット</th>
<th>コマンドレットのパラメーター</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\ Enabled</p></td>
<td><p>サーバーによって送信されるポート範囲を、メディアとシグナリングのクライアントで使うかどうかを指定します。 Subvalues MinMediaPort と MaxMediaPort と組み合わせて使用されます。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>メディアに使用する開始ポート番号を指定します。 MaxMediaPort と組み合わせて、ポートの範囲を指定します。 推奨される最小範囲は、40ポートです。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (クライアントメディアに使用する開始ポート番号を表します)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>メディアに使用する最大のポート番号を指定します。 MinMediaPort と組み合わせて、ポートの範囲を指定します。 推奨される最小範囲は、40ポートです。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (クライアントメディアで利用できるポートの合計数を示します。既定は 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>メディアポート範囲の設定を構成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のコマンドレットを実行します。
    
        Get-CsConferencingConfiguration
    
    このコマンドレットは会議の構成設定を返します。

3.  変更するパラメーターと値を使用して、次のコマンドレットを実行します (このコマンドレットのパラメーターの詳細については、「Lync Server 管理シェルドキュメント」を参照してください)。
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 特定のサイトの会議構成設定の追加のセットを作成できます。 サイト id を使用して<STRONG>CsConferencingConfiguration</STRONG>コマンドレットを使用します。 サイトの新しい会議構成設定を作成する場合、サイトの設定はグローバル設定よりも優先されます。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

