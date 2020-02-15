---
title: Lync Server 2013 IM およびプレゼンス
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
ms.openlocfilehash: 5a7713f7b09602aed01ac20e5a76a361e04277a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013 の IM およびプレゼンス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

インスタントメッセージング (IM) とプレゼンスは、任意の Lync Server 展開に自動的にインストールされます。

*プレゼンス*情報を使用すると、ユーザーは適切なコミュニケーション方法を使用して、適切なタイミングで仕事仲間にアプローチし、より生産性の高い作業環境にすることができます。 ユーザーのプレゼンスとは、空き時間、コミュニケーションの意思、追加のメモ (場所や状態など)、およびユーザーに連絡する方法を含む情報のコレクションです。 プレゼンスが Lync Server で拡張され、画像、場所情報、および "使用可能"、"通話中"、"会議中" などの基本状態に加えて、"作業時間"、"応答不可"、"その他" などのプレゼンス状態の豊富なセットが含まれています。 管理者は、カスタマイズされた組織固有のプレゼンス状態を定義することもできます。

ユーザーは、連絡先の管理とユーザー アクセスのオプションを使って、他のユーザーが表示できる情報を制御できます。ユーザーは異なるレベルの連絡先を設定でき、それぞれの連絡先は異なるレベルのプレゼンス情報を表示できます。

連絡先リストを見るだけで、ユーザーは知る必要があるすべての情報を一目で確認できます。シンプルな色付きのアイコンは他のユーザーのプレゼンス状態を示し、写真や場所も表示されます。

Lync Server と Outlook や SharePoint などの他の製品との統合により、電子メールメッセージやチームの web サイトなどの連絡先の名前が表示されるたびに、状態と連絡先の情報も表示されます。 さらに、Exchange 2013 を展開すると、Lync Server と Exchange 2013 は、いずれかの製品のクライアントがアクセスできる統合連絡先ストアを共有できます。

Lync Server でインスタントメッセージングを使用すると、ユーザーはタイムリーに情報をすばやくメッセージすることができます。 必要に応じて、ユーザーは MSN、Windows Live、Yahoo\!、AOL などのパブリック IM ネットワークのユーザーと通信することもできます。 Windows Live、AOL、および Yahoo とのパブリック IM 接続には、個別のライセンスが必要になる場合があることに注意してください。\! Lync Server には、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) の互換性もあります。このため、ユーザーは、Google Talk などの XMPP サービスのユーザーと IM メッセージやプレゼンス情報を交換できます。

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

会話履歴では、古い IM 会話の経過をたどることができ、何か月も前に IM でやり取りした可能性のある情報を取得できます。

常設チャット機能を使用すると、ユーザーは、時間の経過とともに保持されるマルチパーティのトピックベースの会話に参加できます。 チャット ルーム (ディスカッション フォーラム) に投稿されたメッセージは永続的 (すなわち、長期間使用可能) にできるので、異なる場所や部門に所属するユーザーが常に同時にオンラインでない場合でも会話に参加できます。

組織で法令上の規制に従う必要がある場合、メッセージ アーカイブ機能を展開し、組織内のすべてのユーザーまたは指定した一部のユーザーのみのインスタント メッセージの内容をアーカイブできます。 Exchange 2013 も展開する場合、IM アーカイブを Exchange のインプレースホールド機能と統合して、コンプライアンスに対して単一の管理環境を提供することができます。

</div>

<span> </span>

</div>

</div>

</div>

