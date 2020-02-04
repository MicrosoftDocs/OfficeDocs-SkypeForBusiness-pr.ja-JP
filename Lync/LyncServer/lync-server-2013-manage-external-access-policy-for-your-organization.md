---
title: 'Lync Server 2013: 組織の外部アクセス ポリシーの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Lync Server 2013 での組織の外部アクセス ポリシーの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

1つ以上のエッジサーバーを展開した後は、組織でサポートされる外部アクセスの種類を有効にする必要があります。

既定では、組織の外部ユーザーアクセスのサポートを有効にしている場合でも、リモートユーザーアクセス、フェデレーションされたユーザーアクセスなどの外部ユーザーアクセスをサポートするように構成されたポリシーはありません。 外部ユーザーアクセスの使用を制御するには、1つ以上のポリシーを構成して、各ポリシーでサポートされている外部ユーザーアクセスの種類を指定する必要があります。 作成と構成では、次のポリシースコープを使用できます。 既定では、グローバルポリシーは作成されますが、削除することはできません。

  - **グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。 既定では、グローバルポリシーで外部ユーザーアクセスオプションは有効になっていません。 グローバルレベルで外部ユーザーのアクセスをサポートするには、1つ以上の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。 グローバルポリシーは組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーを上書きします。 グローバルポリシーを削除しても、削除されることはありません。 代わりに、既定の設定にリセットします。

  - **サイトポリシー**   1 つ以上のサイトポリシーを作成し、構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。 サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。 たとえば、グローバルポリシーでリモートユーザーアクセスを有効にする場合、特定のサイトのリモートユーザーアクセスを無効にするサイトポリシーを指定することができます。 既定では、サイトポリシーはそのサイトのすべてのユーザーに適用されますが、サイトポリシー設定を上書きするユーザーポリシーをユーザーに割り当てることができます。

  - **ユーザーポリシー**   1 つまたは複数のユーザーポリシーを作成および構成して、リモートユーザーアクセスのサポートを特定のユーザーに制限することができます。 ユーザーポリシーの構成は、グローバルポリシーおよびサイトポリシーを上書きしますが、ユーザーポリシーが割り当てられている特定のユーザーに対してのみ設定されます。 たとえば、グローバルポリシーとサイトポリシーでリモートユーザーアクセスを有効にすると、リモートユーザーアクセスを無効にするユーザーポリシーを指定して、そのユーザーポリシーを特定のユーザーに割り当てることができます。 ユーザーポリシーを作成する場合は、それを有効にする前に1人以上のユーザーに適用する必要があります。

<div>


> [!IMPORTANT]  
> 1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。



</div>

これらのオプションには、次のような外部アクセスがあります。

  - **フェデレーションされたユーザー**   との通信を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。 この設定では、ユーザーが他の SIP フェデレーションドメインと、Microsoft Office 365 などのホストされるプロバイダーと通信する機能を構成します。 この設定を選択すると、XMPP フェデレーションドメインとの通信を許可するオプションを選択できます。
    
    オプションとして、[フェデレーションされた**ユーザーとの通信を有効**にする] を選択した場合は、[ **xmpp フェデレーションパートナーとの通信を有効**にする] を選択できます。 XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) を使用する組織とのフェデレーションです。
    
    <div>
    

    > [!NOTE]  
    > XMPP フェデレーションを有効にした場合、トポロジビルダーの Edge プール構成セクションで、[ <STRONG>xmpp フェデレーション</STRONG>の展開] も選択する必要があります。 XMPP フェデレーション用に構成すると、microsoft Edge サーバー上の XMPP プロキシと、フロントエンドサーバー上の XMPP ゲートウェイが展開されます。

    
    </div>

  - **[リモートユーザー**   との通信を有効にする] 出張中の在宅勤務者やユーザーなど、組織内のユーザーがインターネット経由で Lync Server に接続できるようにする場合は、このオプションを有効にします。

  - **[パブリックユーザー**   との通信を有効にする] このオプションは、内部ユーザーが、Windows Live、Yahoo\!、America Online (AOL) によって提供される連絡先などのパブリック IM プロバイダーの連絡先と通信できるようにする場合に有効にします。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
    > <LI>
    > <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 外部ユーザーアクセスのサポートを有効にするだけでなく、ユーザーが外部ユーザーアクセスを利用できるようにする前に、組織で外部ユーザーアクセスの使用を制御するためのポリシーも構成する必要があります。 外部ユーザーアクセスのポリシーの作成、構成、適用の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。



</div>

**Windows PowerShell コマンドレットを使用して外部アクセスポリシーを表示するには**

  - Lync Server 管理シェルと**CsExternalAccessPolicy**コマンドレットを使用して、外部アクセスポリシーを表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。
    
    すべての外部アクセスポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsExternalAccessPolicy
    
    このコマンドは、次のような情報を返します。
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Lync Server 2013 外部ユーザー アクセス ポリシーのリセットまたは削除](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

