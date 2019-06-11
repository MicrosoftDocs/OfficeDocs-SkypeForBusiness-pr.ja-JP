---
title: 'Lync Server 2013: 信頼できるアプリケーションの一覧を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23866bfbc437d87911a84d065ae7f501c7d80466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Lync Server 2013 で信頼済みアプリケーションの一覧を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

Lync Server 2013 コントロールパネルを使用して、Lync Server 2013 環境に展開した信頼済みアプリケーションの一覧を表示することができます。 信頼されたアプリケーションは、Lync Server 2013 によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。 この信頼関係は、次の一覧にまとめられています。

  - 信頼されたアプリケーションは、Lync Server による認証の対象にはなりません。

  - SIP トランザクション、接続、またはボイスオーバーインターネットプロトコル (VoIP) 通話の場合、信頼済みアプリケーションは Lync Server によって調整されません。

  - 信頼されたアプリケーションは、選手名簿に表示されることなく、任意のユーザーを偽装し、会議に参加することができます。

  - 信頼性の高いアプリケーションは、高可用性と回復性を備えています。

Lync Server コントロールパネルには、アプリケーションの名前、実行されているプール、および使用しているポートが表示されます。

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>信頼されているアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 Lync Server 2013 で利用できる定義済みの管理者ロールの詳細については、「 [Lync server 2013 でのロールベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**信頼済みアプリケーション**] をクリックします。

4.  [**信頼済みアプリケーション**] ページで、必要に応じて、アプリケーションを並べ替える列見出しをクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

