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
ms.openlocfilehash: b7885d17e708f2073006131862f06d93d9057fb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのパブリックインスタントメッセージング接続の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

パブリックインスタントメッセージング接続はフェデレーションのクラスであり、内部および外部の Lync Server 2013 ユーザーが次のいずれかから連絡先を追加できるように構成されています。

  - Messenger の連絡先

  - !\! 連絡先

  - America Online (AOL) の連絡先

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスのシャットダウン日までメッセンジャーを終了します。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月間のサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されましたが、その基となる契約は更新されません。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されるため、Lync ユーザーは IM や音声を通じて数百人の何百万ものユーザーに連絡できます。</P></LI></UL>



</div>

このクラスのフェデレーションには、次の計画の考慮事項が必要です。

  - Windows Live Messenger ユーザーは、インスタントメッセージに加えて、Lync Server 2013 ユーザーとのピアツーピアの音声/視覚的コミュニケーションを行うことができます。 エッジサーバーは、特定のポートとプロトコルの要件を満たしている必要があります。 詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。

  - Yahoo インスタントメッセージには、フェデレーションを提供している一般的なエッジサーバーの計画と展開で通常使用される要件以外の固有の要件はありません。

  - America Online では、アクセスエッジサービスに割り当てられるエッジサーバー証明書に、クライアント拡張キー使用法 (EKU) が含まれている必要があります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [ポートの概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

