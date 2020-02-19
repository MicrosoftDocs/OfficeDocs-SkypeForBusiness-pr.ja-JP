---
title: 'Lync Server 2013: 信頼されたアプリケーションの一覧を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 866286215389b0e446392bffe3e33f56a767f2e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Lync Server 2013 で信頼されたアプリケーションの一覧を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync server 2013 コントロールパネルを使用して、Lync Server 2013 環境に展開した信頼されたアプリケーションの一覧を表示できます。 信頼されたアプリケーションは、Lync Server 2013 によって信頼されている Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 コア SDK に基づくアプリケーションです。 この信頼関係は、次の一覧に要約されています。

  - 信頼されたアプリケーションは、Lync Server による認証にチャレンジされません。

  - 信頼されたアプリケーションは、SIP トランザクション、接続、または発信ボイスオーバー Ip (VoIP) 呼び出しで Lync Server によって調整されることはありません。

  - 信頼されたアプリケーションは、すべてのユーザーを偽装し、名簿に表示されることなく会議に参加できます。

  - 信頼されたアプリケーションは、高い可用性と復元性を備えています。

Lync Server コントロールパネルには、アプリケーションの名前、実行されているプール、および使用しているポートが表示されます。

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「 [Lync server 2013 で役割ベースのアクセス制御を計画する](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**信頼さ**れたアプリケーション] をクリックします。

4.  [**信頼さ**れたアプリケーション] ページで、必要に応じて列の見出しをクリックしてアプリケーションを並べ替えます。

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

