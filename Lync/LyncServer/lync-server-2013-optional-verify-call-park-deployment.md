---
title: 'Lync Server 2013: (オプション) コールパーク展開の確認'
description: 'Lync Server 2013: (オプション) コールパーク展開を確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541933"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>オプションLync Server 2013 でのコールパーク展開の確認

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-11_

コールパークをインストールして構成した後、構成を検証して、駐車が期待どおりに動作することを確認する必要があります。 少なくとも、以下を確認してください。

  - コールパークが有効になっていて、ユーザーが通話をパークできるユーザーを呼び出します。
    
    <div>
    

    > [!NOTE]  
    > このテストを実行する直前に、音声ポリシーでコールパークを有効にした場合、その通話が参加しているユーザーは、Lync Server からサインアウトしてから再度サインインする必要があります。転送通話リストにコールパークオプションが表示されます。

    
    </div>

  - オービット番号をダイヤルして、電話を取ります。

  - 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

