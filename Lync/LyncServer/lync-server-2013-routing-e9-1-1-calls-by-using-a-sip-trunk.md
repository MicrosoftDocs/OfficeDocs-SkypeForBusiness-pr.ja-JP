---
title: 'Lync Server 2013: SIP トランクを使用した E9-1-1 通話のルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d58507d72a096cb3fbf6deb0d09cddc542fdc2d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013 での SIP トランクを使用した E9-1-1 通話のルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

E9-1-1 を展開する方法に、SIP トランクを使用して、認定された E9-1-1 サービス プロバイダーに接続するという方法があります。 ELIN ゲートウェイを使用して公衆交換電話網 (PSTN) ベースの E9-1-1 サービスプロバイダーに接続する方法の詳細については、「 [E9-1-1 呼び出しを Lync Server 2013 の ELIN ゲートウェイを使用](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)してルーティングする」を参照してください。

次の図は、SIP トランクを使用して、E9-1-1 サービスプロバイダーを修飾した場合に、Lync Server からパブリックの安全応答ポイント (PSAP) に緊急通話をルーティングする方法を示しています。

**SIP トランクを介した E9-1-1 通話のルーティング**

![Lync Server から PSAP への緊急通話のルーティング](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Lync Server から PSAP への緊急通話のルーティング")

対応する Lync Server クライアントから緊急電話が発信された場合:

1.  場所、発信者のコールバック番号、および (オプションで) 通知 URL と会議のコールバック番号を含む SIP INVITE が Lync Server にルーティングされます。

2.  Lync Server は、緊急番号に一致し、(該当する場所ポリシーで定義されている**PSTN 使用法**の値に基づいて) 仲介サーバーに通話をルーティングし、そこから SIP トランクを介して E9-1-1 サービスプロバイダーに通話をルーティングします。

3.  E9-1-1 サービス プロバイダーは、緊急電話と一緒に提供される場所情報に基づいて、通話を適切な PSAP にルーティングします。クライアントが、有効な緊急応答ロケーション (ERL) を緊急電話に含めている場合、プロバイダーはその通話を適切な PSAP に自動転送します。場所情報がユーザーによって手動入力されたものである場合、緊急通話応答センター (ECRC) は、緊急電話を PSAP にルーティングする前に、まず場所が正確かどうかを発信者に口頭で確認します。

4.  通知の場所のポリシーを構成した場合は、1つまたは複数の組織のセキュリティ担当者に対して、特別な Lync 緊急通知インスタントメッセージが送信されます。 このメッセージはセキュリティ担当者の画面に必ずポップアップ表示され、そこには発信者の名前、電話番号、時刻、および場所も含まれているので、セキュリティ担当者はインスタント メッセージまたは音声によってその緊急通話発信者に迅速に応答できます。

5.  場所ポリシーを会議用に構成した場合、E9-1-1 サービス プロバイダーでも会議機能がサポートされているときは、社内のセキュリティ デスクが一方向音声または双方向の音声で通話に参加します。

6.  通話が途中で終了した場合、PSAP はコールバック番号を使用して発信者に直接連絡します。

</div>

<span> </span>

</div>

</div>

</div>

