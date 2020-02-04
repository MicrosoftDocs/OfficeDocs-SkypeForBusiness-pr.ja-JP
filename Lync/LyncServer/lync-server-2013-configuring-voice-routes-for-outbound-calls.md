---
title: 'Lync Server 2013: 発信通話用のボイス ルートの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Lync Server 2013 での発信通話用のボイス ルートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server 2013 のボイスルーティングは、1つ以上の公衆交換電話網 (PSTN) ゲートウェイまたは SIP trunks と1つ以上の PSTN 使用状況レコードとの接続先電話番号を関連付けます。

**Lync Server コントロールパネルを使用して音声ルートを表示するには**

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  [**音声ルーティング**] をクリックします。

3.  [**ルート**] をクリックします。

4.  ボイスルートをダブルクリックして、音声ルートの一覧からその他のプロパティを表示するか、ルートを選んで [**編集**] をクリックします。 次に、[**詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に1つのルートの詳細情報のみを表示することができます。

    
    </div>

**Windows PowerShell を使用して音声ルートを表示するには**

  - Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。 音声ルートを表示するには、Windows PowerShell と**CsVoiceRoute**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。
    
    すべての音声ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsVoiceRoute
    
    次のような情報が表示されます。
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> 詳細については、計画ドキュメントの「 <A href="lync-server-2013-voice-routes.md">Lync Server 2013 の音声ルート</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)

  - [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングの管理](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

