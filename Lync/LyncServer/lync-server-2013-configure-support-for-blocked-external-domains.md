---
title: 'Lync Server 2013: ブロックされた外部ドメインのサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1b7b1da08a8c573b782474d7f2deb4ea9358a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Lync Server 2013 で禁止された外部ドメインのサポートを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

フェデレーション パートナーに対するサポートが構成されている場合、組織とのフェデレーションを禁止するドメインを管理できます。 このオプションが有効な場合は、禁止されているドメインの一覧は禁止リスト (許可されていない明示的なエントリの一覧) として機能し、フェデレーション ドメインの検出時に適用されます。 詳細については、「 [Lync Server 2013 でのフェデレーションパートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)」を参照してください。

1 つまたは複数の外部ドメインの組織への接続を禁止します。この構成を実行するには、ドメインを禁止ドメインの一覧に追加します。

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>外部ドメインを禁止ドメインの一覧に追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックします。

4.  [**フェデレーション ドメイン**] をクリックし、[**新規**] をクリックし、[**禁止ドメイン**] をクリックします。

5.  [**新規フェデレーション ドメイン**] で、次の操作を実行します。
    
      - [**ドメイン名 (または FQDN)**] で、禁止するフェデレーション パートナー ドメインの名前を入力します。
        
        <div>
        

        > [!NOTE]  
        > 名前の長さは、最大 256 文字です。<BR>フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、<STRONG>contoso.com</STRONG> と入力すると、検索によりドメイン <STRONG>it.contoso.com</STRONG> も戻されます。<BR>フェデレーション パートナー ドメインを同時に禁止および許可することはできません。 Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。

        
        </div>
    
      - (オプション) [**コメント**] で、この構成について他のシステム管理者と共有する必要のある情報を入力します。

6.  [**確定**] をクリックします。

7.  禁止するフェデレーション パートナーごとに、ステップ 4 ～ 6 を繰り返します。

フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。 詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。

また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

