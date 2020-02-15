---
title: 'Lync Server 2013: Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8aac965a375520ac46534846a65b67e6d9f92c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync server コントロールパネルを使用して、Lync Server 2013 環境で実行する Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にすることができます。 これらのアプリケーションは、Microsoft Lync 2013 Preview API ではなくスクリプト言語を使用する、スクリプトのみのアプリケーションです。

すべてのスクリプトを有効または無効にできるわけではありません。 たとえば、DefaultRouting スクリプトが有効ですが、このオプションでは DefaultRouting を変更できません。

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>MSPL サーバー アプリケーションを有効または無効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**サーバー アプリケーション**] をクリックします。

4.  [**サーバー アプリケーション**] ページで、必要があれば列見出しをクリックしてアプリケーションを並べ替えてから、変更するサーバー アプリケーションをクリックします。

5.  [**アクション**] をクリックします。

6.  [**アプリケーションを有効にする**] または [**アプリケーションを無効にする**] をクリックします (スクリプトがこのオプションをサポートする場合に実行できます)。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で、Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

