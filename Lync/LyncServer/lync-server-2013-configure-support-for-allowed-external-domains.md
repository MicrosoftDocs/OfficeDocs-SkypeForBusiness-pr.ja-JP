---
title: 'Lync Server 2013: 許可された外部ドメイン向けサポートの構成'
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
ms.openlocfilehash: 31aa2ab9db9ffccd3acda90e9651dfad20b85e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Lync Server 2013 での、許可された外部ドメイン向けサポートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

フェデレーションパートナーのサポートを構成している場合、組織とフェデレーションできる特定のドメインを管理することができます。 1つ以上の特定の外部ドメインを、許可されたフェデレーションドメインとして構成します。 そのためには、許可ドメインの一覧に各ドメインを追加します。 組織でパートナーの検出が有効になっている場合でも、ドメインが1000以上のユーザーと通信する必要がある、または1秒あたり20件を超えるメッセージを送信する必要があるフェデレーションパートナーである場合に、この操作を行います。 組織でパートナー検出が有効になっていない場合、許可されたドメインリストに追加した外部ドメインのユーザーのみが、組織内のユーザーと IM および会議に参加できます。 フェデレーションドメインへのアクセスをフェデレーションパートナーのアクセスエッジサービスを実行している特定のサーバーに制限する場合は、許可ドメインの一覧で、各ドメインのアクセスエッジサービスを実行しているサーバーのドメイン名を指定できます。

<div>


> [!NOTE]  
> この手順では、特定のドメインのサポートを構成する方法について説明します。フェデレーションユーザー向けのサポートを実装するには、組織のフェデレーションユーザーのサポートを有効にする必要があります。また、ポリシーを構成して適用して、ユーザーを管理することもできます。フェデレーションされたユーザーとの共同作業 フェデレーションユーザーのサポートを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。 フェデレーションを制御するためのポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>許可ドメインの一覧に外部ドメインを追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**フェデレーションドメイン**] をクリックします。

4.  [**フェデレーションドメイン**] ページで、[**新規作成**] をクリックし、[許可した**ドメイン**] をクリックします。

5.  **新しいフェデレーションドメイン**で、次の操作を行います。
    
      - [ **Domain name (または FQDN)**] に、フェデレーションパートナードメインの名前を入力します。
        
        <div>
        

        > [!NOTE]  
        > この名前は一意であり、アクセスエッジサービスを実行しているこのサーバーで許可されているドメインとして既に存在することはできません。 名前の長さは、256文字以下にすることはできません。<BR>フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。 たとえば、 <STRONG>contoso.com</STRONG>と入力すると、検索によってドメイン<STRONG>it.contoso.com</STRONG>も返されます。<BR>フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。 Lync Server 2013 では、リストを同期する必要がないように、この問題を回避することができます。

        
        </div>
    
      - このフェデレーションドメインへのアクセスを、アクセスエッジサービス **(FQDN)** で実行されている特定のサーバーのユーザーに制限する場合は、アクセスエッジサービスを実行しているフェデレーションドメインのサーバーの FQDN を入力します。
    
      - 追加情報を提供する場合は、[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。

6.  [**コミット**] をクリックします。

7.  許可するフェデレーションパートナードメインごとに、手順 4 ~ 6 を繰り返します。

フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。 詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。

さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

