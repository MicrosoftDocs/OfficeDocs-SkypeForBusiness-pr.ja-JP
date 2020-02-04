---
title: 'Lync Server 2013: リモート ユーザー アクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8542e7d64198cb83df58885b9240e07066288d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

1つ以上の外部ユーザーアクセスポリシーを構成して、リモートユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。 リモートユーザーアクセスを制御するには、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。 サイトポリシーはグローバルポリシーを上書きし、ユーザーポリシーはサイトとグローバルポリシーを上書きします。 構成できるポリシーの種類の詳細については、「 [Lync Server 2013 に対するフェデレーションと外部アクセスを管理する](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。 1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

<div>


> [!NOTE]  
> 組織のリモートユーザーアクセスを有効にしていない場合でも、リモートユーザーアクセスを制御するポリシーを構成できます。 ただし、構成したポリシーは、組織のリモートユーザーアクセスが有効になっている場合にのみ有効になります。 リモートユーザーアクセスを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効</A>にする」を参照してください。 さらに、リモートユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。 リモートの場所から Lync Server にサインインできるユーザーの指定の詳細については、「 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 で lync を有効にしたユーザーに外部ユーザーアクセスポリシーを割り当てる</A>」を参照してください。



</div>

リモートユーザーアクセスを制御するために使用する外部アクセスポリシーをそれぞれ構成するには、次の手順を使用します。

<div>


> [!NOTE]  
> この手順では、リモートユーザーとの通信を可能にするようにポリシーを構成する方法について説明します。ただし、リモートユーザーアクセスをサポートするように構成した各ポリシーでは、フェデレーションされたユーザーアクセスとパブリックユーザーアクセスを構成することもできます。 フェデレーションユーザーをサポートするポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。 パブリックユーザーをサポートするためのポリシーの構成の詳細については、「 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でパブリック SIP フェデレーションプロバイダーを作成または編集</A>する」を参照してください。



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>外部アクセスポリシーを構成してリモートユーザーのアクセスをサポートするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。
    
      - リモートユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
      - 新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。 [**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。
    
      - 新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。 [**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、リモートユーザーの通信を有効にするユーザーポリシーの**EnableRemoteUsers** )。
    
      - 既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。

6.  次のいずれかを実行します。
    
      - ポリシーのリモートユーザーアクセスを有効にするには、[**リモートユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - ポリシーのリモートユーザーアクセスを無効にするには、[**リモートユーザーとの通信を有効に**する] チェックボックスをオフにします。

7.  [**コミット**] をクリックします。

リモートユーザーアクセスを有効にするには、組織内のリモートユーザーアクセスのサポートも有効にする必要があります。 詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。

ユーザーポリシーの場合は、リモートで接続できるようにするユーザーにもポリシーを適用する必要があります。 詳細については、「展開ドキュメントまたは運用ドキュメントの[Lync Server 2013 で lync を有効にしたユーザーに外部ユーザーアクセスポリシーを割り当てる](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

