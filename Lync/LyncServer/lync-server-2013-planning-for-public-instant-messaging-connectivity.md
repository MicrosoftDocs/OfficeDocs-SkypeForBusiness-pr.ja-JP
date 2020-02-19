---
title: 'Lync Server 2013: パブリックインスタントメッセージング接続の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06b650b277e10214be35414568f2c539f8dd21b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのパブリックインスタントメッセージング接続の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

パブリックインスタントメッセージング接続はフェデレーションのクラスであり、内部および外部の Lync Server 2013 ユーザーが次のいずれかの連絡先を追加できるように構成されています。

  - メッセンジャーの連絡先

  - Yahoo\! contacts

  - America Online (AOL) の連絡先

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規購入または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 サービスの終了日までの Messenger。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月あたりのサブスクリプションライセンスです。 Messenger. このサービスを提供する Microsoft の機能は、Yahoo! からのサポートを受けています。これは、更新されない基になる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を通じて数十万のユーザーにアクセスできるようになります。</P></LI></UL>



</div>

このクラスのフェデレーションには、計画に関する次のような考慮が必要です。

  - Windows Live Messenger ユーザーは、インスタントメッセージングに加えて、Lync Server 2013 ユーザーとのピアツーピアの音声ビデオ通信を行うことができます。 エッジサーバーは、特定のポートとプロトコルの要件を満たす必要があります。 詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を確認する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。

  - Yahoo インスタントメッセージングには、フェデレーションを提供する一般的なエッジサーバーの計画と展開で通常使用される要件以外に、固有の要件はありません。

  - America Online では、アクセスエッジサービスに割り当てられているエッジサーバー証明書にクライアント拡張キー使用法 (EKU) が含まれている必要があります。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [ポートの概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

