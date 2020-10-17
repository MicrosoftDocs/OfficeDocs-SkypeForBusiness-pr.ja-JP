---
title: 'Lync Server 2013: 発信通話用のボイスルートの構成'
description: 'Lync Server 2013: 発信通話用のボイスルートの構成。'
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
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542213"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Lync Server 2013 での発信通話の音声ルートの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 voice route は、宛先の電話番号を1つまたは複数の公衆交換電話網 (PSTN) ゲートウェイまたは SIP トランクおよび1つ以上の PSTN 使用法レコードに関連付けます。

**Lync Server コントロールパネルを使用して音声ルートを表示するには**

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  [**音声のルーティング**] をクリックします。

3.  [**ルート**] をクリックします。

4.  音声ルートをダブルクリックし、音声ルートの一覧から追加のプロパティを表示するか、ルートを選択し、[**編集**] をクリックします。次に、[**詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に 1 つのルートの詳細情報しか表示できません。

    
    </div>

**Windows PowerShell を使用して音声ルートを表示するには**

  - Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。 音声ルートは、Windows PowerShell と **get-csvoiceroute** コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。
    
    すべての音声ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
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
> 詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-voice-routes.md">Voice 回送 In Lync Server 2013</A> 」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

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

