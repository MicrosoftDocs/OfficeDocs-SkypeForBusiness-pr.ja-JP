---
title: 'Lync Server 2013: 禁止された外部ドメイン向けサポートの構成'
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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Lync Server 2013 での禁止された外部ドメイン向けサポートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

フェデレーションパートナーのサポートを構成している場合は、どのドメインを組織とのフェデレーションからブロックするかを管理できます。 ブロックされたドメインの一覧はブロックリスト (許可されていない明示的なエントリの一覧) として機能し、このオプションを有効にしている場合はフェデレーションドメインの検出に適用されます。 詳細については、「 [Lync Server 2013 でフェデレーションパートナーの検出を有効または無効](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)にする」を参照してください。

1つ以上の外部ドメインをブロックして組織に接続します。 そのためには、ブロックされたドメインの一覧にドメインを追加します。

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>ブロックされたドメインの一覧に外部ドメインを追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックします。

4.  [**フェデレーションドメイン**] をクリックし、[**新規作成**] をクリックして、[**禁止ドメイン**] をクリックします。

5.  **新しいフェデレーションドメイン**で、次の操作を行います。
    
      - [ **Domain name (または FQDN)**] に、ブロックするフェデレーションパートナードメインの名前を入力します。
        
        <div>
        

        > [!NOTE]  
        > 名前の長さは、256文字以下にすることはできません。<BR>フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。 たとえば、 <STRONG>contoso.com</STRONG>と入力すると、検索によってドメイン<STRONG>it.contoso.com</STRONG>も返されます。<BR>フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。 Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。

        
        </div>
    
      - 省略[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。

6.  [**コミット**] をクリックします。

7.  ブロックするフェデレーションパートナーごとに、手順 4 ~ 6 を繰り返します。

フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。 詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。

さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

