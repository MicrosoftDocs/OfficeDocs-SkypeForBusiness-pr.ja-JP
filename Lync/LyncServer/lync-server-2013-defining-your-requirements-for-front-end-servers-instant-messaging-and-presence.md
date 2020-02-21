---
title: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスの要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9be82373d33dafba7a5cf3e967b162ab5d33b01e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

インスタント メッセージング (IM) とプレゼンスの計画における主なタスクは、ユーザーのために十分な数のフロント エンド サーバーを確保することです。

<div>

## <a name="enabling-communication-with-external-users"></a>外部ユーザーとの通信の有効化

ユーザーが外部ユーザーと通信できるようにすることで、Lync Server に対する投資のメリットを大幅に向上させることができます。 外部ユーザーには次のユーザーが含まれます。

  - **リモートユーザー**   ファイアウォールの外側で作業し、ラップトップやその他の Lync Server デバイスを使用している場合は、組織のユーザーを所有します。

  - ****   Lync Server を実行しているユーザーと共同で作業する企業のフェデレーションユーザー。 こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。

  - **パブリックユーザー**   インターネットサービス、Yahoo\!、AOL の Windows Live ネットワークによって提供される im サービスなどのパブリック im サービスのユーザー、および Google Talk などの拡張可能なメッセージングとプレゼンスプロトコル (xmpp) を使用するプロバイダーおよびサーバーのユーザー。
    
    <div>
    

    > [!NOTE]  
    > ただし、Windows Live、AOL、Yahoo! とのパブリック IM 接続には、個別のライセンスが必要な場合があります。

    
    </div>
    
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

これらのシナリオのいずれかまたはすべてを有効にするには、Lync server の展開と外部ユーザーとの間でセキュリティで保護された通信を有効にするためにエッジサーバーを展開する必要があります。 組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して互いのプレゼンスと通信を確認できるようになります。 外部ユーザーとの通信の有効化の詳細については、「計画」のドキュメントの「 [planning for external user access In Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) 」を参照してください。

</div>

<div>

## <a name="archiving-im-content"></a>IM コンテンツのアーカイブ

Lync Server は、組織が法令遵守規制に従う必要がある場合に使用できる機能を提供します。 アーカイブを使用すると、組織内のすべてのユーザーまたは指定した特定のユーザーに対して、IM メッセージの内容をアーカイブすることができます。 詳細については、「計画」のドキュメントの「 [planning For アーカイビング In Lync Server 2013](lync-server-2013-planning-for-archiving.md) 」を参照してください。

Microsoft Exchange Server 2013 が展開されている場合は、Exchange データのアーカイブと Lync Server データのアーカイブを統合し、単一のツールを使用して両方の種類のアーカイブデータを検索することができます。 詳細については、microsoft [Exchange server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

