---
title: 'Lync Server 2013: Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50dea89feb7e72c5076e58a38136d24b1b34499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Lync Server 2013 で、Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API の代わりに MSPL スクリプト言語を使用するスクリプトのみのアプリケーションです。 一部の MSPL サーバーアプリケーションは、重要として指定されています。 スクリプトが重要である場合、Lync Server 2013 を開始するために、スクリプトはシステム起動時に開始する必要があります。 Lync Server の実行中にスクリプトが失敗した場合、サーバーはシャットダウンされませんが、スクリプトへのトラフィックの送信が停止し、エラーがイベントログに記録されます。

Lync Server コントロールパネルを使用して、Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを重要としてマークしたり、アンマークしたりすることができます。

すべてのスクリプトがこのオプションをサポートするわけではありません。 たとえば、DefaultRouting スクリプトは critical としてマークされており、このオプションを DefaultRouting に対して変更することはできません。

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>MSPL サーバーアプリケーションを重要としてマークまたはマークを解除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**トポロジ**] をクリックし、[**サーバー アプリケーション**] をクリックします。

4.  [**サーバー アプリケーション**] ページで、必要があれば列見出しをクリックしてアプリケーションを並べ替えてから、変更するサーバー アプリケーションをクリックします。

5.  [**アクション**] をクリックします。

6.  [重要とし**てマーク**] をクリックするか、[重大] (スクリプトがこのオプションをサポートしている場合) を**選択**します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

