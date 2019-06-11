---
title: 'Lync Server 2013: (オプション) コールパークの展開を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>省略Lync Server 2013 でのコールパークの展開を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-11_

コールパークのインストールと構成が完了したら、構成を確認して、パーキングと着信の取得が期待どおりに動作することを確認する必要があります。 少なくとも、以下を確認してください。

  - コールパークが有効になっていて、ユーザが通話をパークしているユーザに電話をかけます。
    
    <div>
    

    > [!NOTE]  
    > このテストを実行する前に、音声ポリシーでコールパークを有効にしている場合は、その通話を保留にしているユーザーが Lync Server からサインアウトしてから、もう一度サインインすると、[着信の転送] リストの [コールパーク] オプションが表示されます。

    
    </div>

  - オービット番号をダイヤルして、電話を取ります。

  - 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

