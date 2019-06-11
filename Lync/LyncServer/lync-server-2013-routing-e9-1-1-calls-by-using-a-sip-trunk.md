---
title: 'Lync Server 2013: SIP トランクを使用した E9-1-1 通話のルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c537b66883ab786bc28e3cc808874c0fcb79b92d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013 での SIP トランクを使用した E9-1-1 通話のルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

E9-1-1 を展開する方法の 1 つに、SIP トランクを使用して、認定された E9-1-1 サービス プロバイダーに接続する方法があります。 ELIN ゲートウェイを使って公衆交換電話網 (PSTN) ベースの E9 サービスプロバイダーに接続する方法の詳細については、「 [Lync Server 2013 の ELIN ゲートウェイを使用して、E9 通話のルーティング](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)」を参照してください。

次の図は、SIP トランクと認定された E9 1-1 サービスプロバイダを使用している場合に、緊急通話が Lync Server から公共の安全応答ポイント (PSAP) にどのようにルーティングされるかを示しています。

**SIP トランクを使用した E9-1-1 通話のルーティング**

![Lync Server から PSAP への緊急通話ルーティング](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Lync Server から PSAP への緊急通話ルーティング")

対応する Lync Server クライアントから緊急通話を発信した場合:

1.  発信者のコールバック番号と、(省略可能) 通知 URL と会議のコールバック番号を含む SIP 招待は、Lync Server にルーティングされます。

2.  Lync Server は、緊急電話番号に一致し、(該当する場所のポリシーで定義されている**PSTN 使用量**の値に基づく) 通話を仲介サーバーにルーティングします。そこから、SIP トランクを E9 サービスプロバイダーに転送します。

3.  E9-1-1 サービス プロバイダーは、緊急電話と一緒に提供される場所情報に基づいて、通話を適切な PSAP にルーティングします。クライアントが、有効な緊急応答場所 (ERL) を緊急電話に含めている場合、プロバイダーはその通話を適切な PSAP に自動転送します。場所情報がユーザーによって手動入力されたものである場合、緊急通話応答センター (ECRC) は、緊急電話を PSAP にルーティングする前に、まず場所が正確かどうかを発信者に口頭で確認します。

4.  通知の場所のポリシーを構成している場合は、1つ以上の組織のセキュリティ責任者に、Lync 緊急通報に関する特別な通知のインスタントメッセージが送信されます。 このメッセージはセキュリティ担当者の画面に必ずポップアップ表示され、そこには発信者の名前、電話番号、時刻、および場所も含まれているので、セキュリティ担当者はインスタント メッセージまたは音声によってその緊急通話発信者に迅速に応答できます。

5.  場所ポリシーを会議用に構成した場合、E9-1-1 サービス プロバイダーでも会議機能がサポートされているときは、社内のセキュリティ デスクが一方向音声または双方向の音声で通話に参加します。

6.  通話が途中で終了した場合、PSAP はコールバック番号を使用して発信者に直接連絡します。

</div>

<span> </span>

</div>

</div>

</div>

