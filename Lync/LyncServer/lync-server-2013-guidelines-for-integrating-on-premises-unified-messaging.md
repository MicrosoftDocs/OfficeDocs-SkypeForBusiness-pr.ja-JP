---
title: 'Lync Server 2013: オンプレミスのユニファイドメッセージングを統合するためのガイドライン'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f032f7dd7d11d70ac912b2005f3ad9f7ddad69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536924"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-25_

エンタープライズ Voip を展開する際に考慮すべきガイドラインとベストプラクティスを次に示します。

<div>


> [!IMPORTANT]  
> Exchange ユニファイドメッセージング (UM) は、UCMA 4 も使用している場合にのみ、IPv6 をサポートします。



</div>

  - Lync Server 2013 Standard Edition サーバーまたはフロントエンドプールを展開します。 インストールの詳細については、「展開」のドキュメントの「 [展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。

  - スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。

  - Exchange UM に対してユーザーを有効にする各 Exchange ユニファイドメッセージング (UM) フォレストに、Exchange メールボックスサーバーの役割を展開します。 Exchange server の役割のインストールの詳細については、Microsoft Exchange Server 2013 のドキュメントを参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > Exchange ユニファイドメッセージング (UM) がインストールされている場合、自己署名証明書を使用するように構成されます。<BR>ただし、自己署名証明書では、Lync Server 2013 と Exchange UM が相互に信頼することはできません。このため、両方のサーバーが信頼する証明機関に対して個別の証明書を要求する必要があります。

    
    </div>

  - Lync Server 2013 と Exchange UM が異なるフォレストにインストールされている場合は、各 exchange フォレストが Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼するように構成して、各 Exchange フォレストを信頼するようにします。 また、通常は、スクリプトまたは Id ライフサイクルマネージャー (ILM) などのフォレスト間ツールを使用して、Lync Server 2013 フォレスト内のユーザーオブジェクトに対するユーザーの Exchange UM 設定を設定します。

  - 必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。

  - Outlook Voice Access および自動応答の有効な電話番号を取得します。

  - Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合は、Exchange UM SIP URI ダイヤルプランおよびエンタープライズ Voip ダイヤルプランの名前を調整します。

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>冗長 Exchange UM サーバーの展開

<div>


> [!IMPORTANT]  
> 組織に対して構成する Exchange UM SIP URI ダイヤルプランごとに、Exchange UM サービスが実行されているサーバーを少なくとも2台展開することをお勧めします。 拡張された容量の提供に加えて、冗長サーバーを展開すると高可用性が得られます。 サーバー障害が発生した場合、Lync Server 2013 を別のサーバーにフェールオーバーするように構成できます。



</div>

次に示すのは、Exchange UM の復元性を提供する構成例です。

**例 1: Exchange UM の復元性**

![Exchange UM の例1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM の例1")

例1では、データセンターで Exchange UM サーバー1と2が有効になっており、Dublin データセンターで Exchange UM サーバー3と4が有効になっています。 Tuで Exchange UM が停止した場合、サーバー1と2のドメインネームシステム (DNS) A レコードは、それぞれサーバー3と4をポイントするように構成する必要があります。 Dublin で Exchange UM が停止した場合、サーバー3と4の DNS A レコードは、それぞれサーバー1と2をポイントするように構成する必要があります。

<div>


> [!NOTE]  
> 例 1 の場合はまた、それぞれの Exchange UM サーバーで次の証明書のうちの 1 つを割り当てます。 
> <UL>
> <LI>
> <P>サブジェクト名の別名 (SAN) に、ワイルドカードの証明書を使用します。</P>
> <LI>
> <P>SAN 内の4台の Exchange UM サーバーそれぞれの完全修飾ドメイン名 (FQDN) を入力します。</P></LI></UL>



</div>

**例 2:Exchange UM の復元性**

![Exchange UM の例2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM の例2")

例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。 4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー3 と 4 は有効化されていません。 たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。

Exchange 2013 でユニファイドメッセージングを有効または無効にする方法の詳細については、「」の「Exchange 2013 UM と Lync Server の統合」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。

Microsoft Exchange Server 2010 でユニファイドメッセージングを有効または無効にする方法の詳細については、以下を参照してください。

  - 「Exchange 2010 でユニファイドメッセージングを有効 [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) にする」

  - 「Exchange 2010 でユニファイドメッセージングを無効 [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) にする」

</div>

<div>

## <a name="see-also"></a>関連項目


[オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

