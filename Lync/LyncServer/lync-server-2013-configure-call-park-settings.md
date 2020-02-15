---
title: 'Lync Server 2013: コールパーク設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 644ec44d4086b0acc326e043cbf63d7ceb2c640c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Lync Server 2013 でコールパーク設定を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

既定のコールパーク設定を使用しない場合は、それらをカスタマイズできます。 コールパークアプリケーションをインストールすると、既定でグローバル設定が構成されます。 グローバル設定を変更したり、サイト固有の設定を指定したりすることもできます。 新しいサイト固有の設定を作成するには、 **new-cscpsconfiguration**コマンドレットを使用します。 既存の設定を変更するには、 **new-cscpsconfiguration**コマンドレットを使用します。

<div>


> [!NOTE]  
> 少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [<STRONG>OnTimeoutURI</STRONG>] オプションは構成することをお勧めします。



</div>

**New-CsCpsConfiguration** コマンドレットまたは **Set-CsCpsConfiguration** コマンドレットを使用して、次のいずれかの設定を構成します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>このオプション:</th>
<th>指定する内容:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。</p>
<p>この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。 最小値は 10 秒、最大値は 10 分です。 既定値は 00:01:30 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>通話が保留されている間、発信者に対して音楽を再生するかどうか。</p>
<p>値は True または False です。既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>保留された通話が [<strong>OnTimeoutURI</strong>] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>[Ontimeouturi]</strong></p></td>
<td><p><strong>MaxCallPickupAttempts</strong> を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。</p>
<p>値は、文字列 sip: で始まる SIP URI にする必要があります。 たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>コールパーク設定を構成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > サイトを識別するには、<STRONG>Get-CsSite</STRONG> コマンドレットを使用します。 詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

    
    </div>
    
    次に例を示します。
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でコールパーク保留音をカスタマイズする](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[New-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[取得-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

