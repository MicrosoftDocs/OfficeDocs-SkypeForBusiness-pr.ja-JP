---
title: 'Lync Server 2013: 組織の外部アクセスポリシーの管理'
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
ms.openlocfilehash: 3a7a3d612de9cf530e512031b7009a83ad9c391c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Lync Server 2013 での外部アクセスポリシーの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

1つ以上のエッジサーバーを展開した後、組織でサポートされる外部アクセスの種類を有効にする必要があります。

組織で外部ユーザー アクセス (リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど) のサポートを既に有効にしていても、既定では外部ユーザー アクセスをサポートするように構成されているポリシーはありません。外部ユーザー アクセスの使用を制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。ポリシーの作成および構成時に使用できるスコープを次に示します。既定では、グローバル ポリシーが作成されますが、このポリシーを削除することはできません。

  - **グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。 既定では、グローバルポリシーでは、外部ユーザーアクセスオプションが有効になっていません。 グローバルレベルで外部ユーザーアクセスをサポートするには、1つまたは複数の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。 グローバルポリシーは、組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーより優先されます。 グローバルポリシーを削除した場合は、削除しないようにします。 代わりに、既定の設定にリセットします。

  - **サイトポリシー**   1 つ以上のサイトポリシーを作成および構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。 サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。 たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。 既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。

  - **ユーザーポリシー**   1 つ以上のユーザーポリシーを作成および構成して、特定のユーザーへのリモートユーザーアクセスのサポートを制限することができます。 ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。 たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。 ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。

<div>


> [!IMPORTANT]  
> あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。



</div>

これらのオプションには、次の種類の外部アクセスが含まれます。

  - **フェデレーションユーザー**   との通信を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。 この設定では、ユーザーが他の SIP フェデレーションドメインと、Microsoft Office 365 などのホストされるプロバイダーと通信する機能を構成します。 この設定を選択すると、XMPP フェデレーションドメインとの通信を許可するオプションを選択できます。
    
    [**フェデレーション ユーザーとの通信を有効にする**] を選択していれば、必要に応じて、[**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択できます。XMPP フェデレーションは、Extensible Messaging and Presence Protocol (XMPP) を使用する組織とのフェデレーションです。
    
    <div>
    

    > [!NOTE]  
    > XMPP フェデレーションを有効にする場合は、トポロジビルダーのエッジプール構成セクションで<STRONG>xmpp フェデレーション</STRONG>を展開することも選択する必要があります。 XMPP フェデレーションを構成すると、エッジサーバーには XMPP プロキシが展開され、フロントエンドサーバーには XMPP ゲートウェイが展開されます。

    
    </div>

  - **[リモートユーザー**   との通信を有効にする] このオプションを有効にすると、出張中の在宅勤務やユーザーなど、ファイアウォールの外側にいる組織内のユーザーがインターネット経由で Lync Server に接続できるようになります。

  - **[パブリックユーザー**   との通信を有効にする] 内部ユーザーがパブリック IM プロバイダーの連絡先 (Windows Live、Yahoo\!、および America Online (AOL) によって提供される連絡先など) と通信できるようにする場合は、このオプションを有効にします。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
    > <LI>
    > <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 外部ユーザー アクセスのサポートを有効にするだけでなく、ユーザーが任意の種類の外部ユーザー アクセスを使用できるようにする前に、組織内での外部ユーザー アクセスの使用を制御するポリシーも構成する必要があります。 外部ユーザーアクセスのポリシーの作成、構成、および適用の詳細については、「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスの有効化または無効化</A>」を参照してください。



</div>

**Windows PowerShell コマンドレットを使用して外部アクセスポリシーを表示するには**

  - 外部アクセスポリシーは、Lync Server 管理シェルと**get-csexternalaccesspolicy**コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。
    
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

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Lync Server 2013 での Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Lync Server 2013 での外部ユーザーアクセスポリシーのリセットまたは削除](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

