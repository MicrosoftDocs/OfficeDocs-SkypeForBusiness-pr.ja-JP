---
title: Lync Server 2013 IM とプレゼンス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013 IM とプレゼンス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

インスタントメッセージング (IM) とプレゼンスは、任意の Lync Server 展開に自動的にインストールされます。

*プレゼンス*情報を使用すると、ユーザーは適切なコミュニケーション方法で同僚と連絡をとって、より生産的な作業環境を実現できます。 ユーザーのプレゼンスは、空き時間情報、コミュニケーションの意思、その他のメモ (場所と状態など)、およびユーザーに連絡する方法を含む情報の集まりです。 プレゼンスは、Lync Server で、画像、場所情報、および "機能をオフにする"、"応答不可"、"退席中" など、"使用可能"、"取り込み中"、"会議中" などの基本的な状態を含む、プレゼンス状態が強化されています。 管理者は、カスタマイズされた、組織固有のプレゼンス状態を定義することもできます。

[連絡先管理] および [ユーザーアクセス] オプションを使うと、他のユーザーが表示できる情報を制御することができます。 ユーザーは異なるレベルの連絡先を設定することができ、それぞれに異なるレベルのプレゼンス情報を表示できます。

連絡先リストを見るだけで、ユーザーはひとめで知っておく必要がある情報をすべて見つけることができます。 シンプルな色付きのアイコンは、他のユーザーのプレゼンス状態を示します。また、画像と場所も表示されます。

Lync Server と Outlook や SharePoint などの他の製品との統合により、連絡先の名前 (メールメッセージやチームの web サイトなど) が表示されるたびに、状態と連絡先の情報も表示されます。 また、Exchange 2013 を展開した場合、Lync Server と Exchange 2013 では、いずれかの製品のクライアントからアクセスできるユニファイド連絡先ストアを共有できます。

Lync Server でインスタントメッセージングを使用すると、ユーザーはタイムリーな情報を使用して互いに簡単にメッセージを送信できます。 必要に応じて、ユーザーは、MSN、Windows Live、Yahoo\!、AOL などのパブリック IM ネットワークのユーザーと通信することもできます。 Windows Live、AOL、Yahoo とのパブリック IM 接続には個別のライセンスが必要になる場合があることに注意してください。\! Lync Server には、拡張メッセージングとプレゼンスプロトコル (XMPP) の互換性も含まれているため、ユーザーは、Google Talk などの XMPP サービスのユーザーと IM メッセージとプレゼンス情報を交換することができます。

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

会話履歴を使用すると、ユーザーは以前の IM 会話を追跡し、IM 月数前に伝えられた情報を取得することができます。

常設チャット機能を使うと、ユーザーはマルチパーティのトピックベースの会話に参加することができます。これにより、時間の経過と共に維持されます。 チャットルーム (ディスカッションフォーラム) に投稿されたメッセージは、常にオンラインではない場合でも、異なる場所や部門のメンバーが参加できるように、継続的に (つまり、時間の経過と共に利用可能) することができます。

組織でコンプライアンスの規則に従う必要がある場合は、メッセージアーカイブ機能を展開して、組織内のすべてのユーザーに対して、または指定した特定のユーザーのみにインスタントメッセージのコンテンツをアーカイブすることができます。 また、Exchange 2013 を展開する場合は、IM アーカイブを Exchange のインプレースホールド機能と統合することで、コンプライアンスのために単一の管理エクスペリエンスを提供することができます。

</div>

<span> </span>

</div>

</div>

</div>

