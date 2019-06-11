---
title: 'Lync Server 2013: Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419a162e355434972216f0c47d79850af28cd244
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API ではなく、MSPL スクリプト言語を使用するスクリプトのみのアプリケーションです。 一部の MSPL server アプリケーションは critical として指定されています。 スクリプトが重要な場合は、Lync Server 2013 を起動するために、スクリプトがシステムの起動中に開始される必要があります。 Lync Server の実行中にスクリプトが失敗した場合、サーバーはシャットダウンせず、スクリプトへのトラフィック送信が停止し、イベントログにエラーを書き込みます。

Lync Server コントロールパネルを使用して、Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションをクリティカルとしてマークしたり、マークを解除したりすることができます。

すべてのスクリプトでこのオプションがサポートされるわけではありません。 たとえば、DefaultRouting スクリプトは critical とマークされているため、DefaultRouting に対してこのオプションを変更することはできません。

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>MSPL server アプリケーションを重要としてマークまたはマーク解除するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**サーバーアプリケーション**] をクリックします。

4.  [**サーバーアプリケーション**] ページで、必要に応じて、アプリケーションを並べ替える列見出しをクリックし、変更するサーバーアプリケーションをクリックします。

5.  [**アクション**] をクリックします。

6.  [**重要としてマーク**] または [重大] (スクリプトがこのオプションをサポートしている場合) を**選択**します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Lync Server 2013 での Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

