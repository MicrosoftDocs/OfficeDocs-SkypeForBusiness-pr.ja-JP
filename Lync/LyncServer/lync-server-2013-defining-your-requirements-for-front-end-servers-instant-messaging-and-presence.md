---
title: 'Lync Server 2013: フロントエンド サーバー、インスタント メッセージング、およびプレゼンスに関する要件の定義'
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
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 でのフロントエンド サーバー、インスタント メッセージング、およびプレゼンスに関する要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

インスタントメッセージング (IM) とプレゼンスを計画する主なタスクは、ユーザーに対して十分なフロントエンドサーバーがあることを確認することです。

<div>

## <a name="enabling-communication-with-external-users"></a>外部ユーザーとの通信を有効にする

ユーザーが外部ユーザーと通信できるようにすることで、Lync Server での投資の利点を大幅に高めることができます。 外部ユーザーには次のユーザーが含まれます。

  - **リモートユーザー**   は、ファイアウォール外で作業していて、ノート pc やその他の Lync Server デバイスを使用している場合に、組織の独自のユーザーを管理します。

  - ****   Lync Server を実行している企業の会社からフェデレーションされたユーザー。 自社ユーザーがこうしたユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。

  - ****   パブリック im サービスを利用する一般ユーザー (インターネットサービス、Yahoo\!、AOL の Windows Live ネットワークによって提供された im サービス、または Google Talk などの拡張メッセージングとプレゼンスプロトコル (xmpp) を使用するプロバイダーおよびサーバーのユーザー。
    
    <div>
    

    > [!NOTE]  
    > Windows Live、AOL、Yahoo! のパブリック IM 接続には個別のライセンスが必要になる場合があることに注意してください。

    
    </div>
    
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

これらのシナリオのいずれかまたはすべてを有効にするには、お客様が Lync Server の展開と外部ユーザーとの間で安全な通信を実現するために、エッジサーバーを展開する必要があります。 組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して互いのプレゼンスと通信を確認できるようになります。 外部ユーザーとの通信を有効にする方法の詳細については、計画ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

</div>

<div>

## <a name="archiving-im-content"></a>IM コンテンツのアーカイブ

Lync Server には、組織がコンプライアンス規則に従う必要がある場合に使用できる機能が用意されています。 アーカイブを使用すると、組織内のすべてのユーザーまたは指定する特定のユーザーの IM メッセージの内容をアーカイブすることができます。 詳細については、計画ドキュメントの「 [Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)」を参照してください。

Microsoft Exchange Server 2013 が展開されている場合は、Exchange データのアーカイブを Lync Server データのアーカイブと統合することができます。また、単一のツールを使用して、両方の種類のアーカイブデータを検索することもできます。 詳細については、「microsoft [Lync server 2013 で Microsoft Exchange Server 2013 アーカイブを使用するように構成する](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

