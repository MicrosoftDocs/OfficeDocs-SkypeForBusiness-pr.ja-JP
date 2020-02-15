---
title: 'Lync Server 2013: 許可されている外部ドメインのサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Lync Server 2013 で許可された外部ドメインのサポートを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

フェデレーションパートナーのサポートを構成した場合は、組織とフェデレーションできる特定のドメインを管理できます。 1つ以上の特定の外部ドメインを許可されたフェデレーションドメインとして構成します。 これを行うには、許可されるドメインの一覧に各ドメインを追加します。 組織に対してパートナーの検出が有効になっている場合でも、ドメインが1000以上のユーザーと通信する必要があるか、または1秒あたり20件を超えるメッセージを送信する必要があるフェデレーションパートナーである場合に、これを実行します。 パートナー検出が組織で有効になっていない場合は、許可されたドメインリストに追加した外部ドメインのユーザーのみが、組織内のユーザーとの IM および会議に参加できます。 フェデレーションドメインのアクセスを、フェデレーションパートナーのアクセスエッジサービスを実行している特定のサーバーに制限する場合は、許可されたドメインの一覧で、各ドメインのアクセスエッジサービスを実行するサーバーのドメイン名を指定することができます。

<div>


> [!NOTE]  
> この手順では、特定のドメインのサポートを構成する方法について説明しますが、フェデレーションユーザーのサポートを実装するには、組織のフェデレーションユーザーのサポートを有効にし、ポリシーを構成して適用して、どのユーザーが操作できるかを制御する必要もあります。フェデレーションユーザーと共同作業を行います。 フェデレーションユーザーのサポートの有効化の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスの有効化または無効化</A>」を参照してください。 フェデレーションを制御するポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>許可されたドメインの一覧に外部ドメインを追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [**外部ユーザーアクセス**] をクリックし、[**フェデレーションドメイン**] をクリックします。

4.  [**フェデレーションドメイン**] ページで、[**新規**] をクリックし、[**許可さ**れたドメイン] をクリックします。

5.  [**新規フェデレーション ドメイン**] で、次の操作を実行します。
    
      - [**ドメイン名 (または FQDN)**] で、フェデレーションパートナードメインの名前を入力します。
        
        <div>
        

        > [!NOTE]  
        > この名前は一意である必要があり、アクセスエッジサービスを実行しているこのサーバーで許可されているドメインとして既に存在することはできません。 名前の長さは、最大 256 文字です。<BR>フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、<STRONG>contoso.com</STRONG> と入力すると、検索によりドメイン <STRONG>it.contoso.com</STRONG> も戻されます。<BR>フェデレーション パートナー ドメインを同時に禁止および許可することはできません。 Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。

        
        </div>
    
      - アクセスエッジサービスを実行している特定のサーバーのユーザーに対して、このフェデレーションドメインのアクセスを制限する場合は、アクセスエッジサービス **(fqdn)** で、アクセスエッジサービスを実行しているフェデレーションドメインのサーバーの fqdn を入力します。
    
      - 追加情報を提供する場合は、[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。

6.  [**確定**] をクリックします。

7.  許可するフェデレーションパートナードメインごとに、手順 4 ~ 6 を繰り返します。

フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。 詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。

また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

