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
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="4816a-102">Lync Server 2013 での SIP トランクを使用した E9-1-1 通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="4816a-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4816a-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="4816a-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="4816a-104">E9-1-1 を展開する方法の 1 つに、SIP トランクを使用して、認定された E9-1-1 サービス プロバイダーに接続する方法があります。</span><span class="sxs-lookup"><span data-stu-id="4816a-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="4816a-105">ELIN ゲートウェイを使って公衆交換電話網 (PSTN) ベースの E9 サービスプロバイダーに接続する方法の詳細については、「 [Lync Server 2013 の ELIN ゲートウェイを使用して、E9 通話のルーティング](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4816a-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="4816a-106">次の図は、SIP トランクと認定された E9 1-1 サービスプロバイダを使用している場合に、緊急通話が Lync Server から公共の安全応答ポイント (PSAP) にどのようにルーティングされるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="4816a-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="4816a-107">**SIP トランクを使用した E9-1-1 通話のルーティング**</span><span class="sxs-lookup"><span data-stu-id="4816a-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="4816a-108">![Lync Server から PSAP への緊急電話のルーティング](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Lync Server から PSAP への緊急電話のルーティング")</span><span class="sxs-lookup"><span data-stu-id="4816a-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="4816a-109">対応する Lync Server クライアントから緊急通話を発信した場合:</span><span class="sxs-lookup"><span data-stu-id="4816a-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="4816a-110">発信者のコールバック番号と、(省略可能) 通知 URL と会議のコールバック番号を含む SIP 招待は、Lync Server にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="4816a-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="4816a-111">Lync Server は、緊急電話番号に一致し、(該当する場所のポリシーで定義されている**PSTN 使用量**の値に基づく) 通話を仲介サーバーにルーティングします。そこから、SIP トランクを E9 サービスプロバイダーに転送します。</span><span class="sxs-lookup"><span data-stu-id="4816a-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="4816a-p102">E9-1-1 サービス プロバイダーは、緊急電話と一緒に提供される場所情報に基づいて、通話を適切な PSAP にルーティングします。クライアントが、有効な緊急応答場所 (ERL) を緊急電話に含めている場合、プロバイダーはその通話を適切な PSAP に自動転送します。場所情報がユーザーによって手動入力されたものである場合、緊急通話応答センター (ECRC) は、緊急電話を PSAP にルーティングする前に、まず場所が正確かどうかを発信者に口頭で確認します。</span><span class="sxs-lookup"><span data-stu-id="4816a-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="4816a-115">通知の場所のポリシーを構成している場合は、1つ以上の組織のセキュリティ責任者に、Lync 緊急通報に関する特別な通知のインスタントメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="4816a-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="4816a-116">このメッセージはセキュリティ担当者の画面に必ずポップアップ表示され、そこには発信者の名前、電話番号、時刻、および場所も含まれているので、セキュリティ担当者はインスタント メッセージまたは音声によってその緊急通話発信者に迅速に応答できます。</span><span class="sxs-lookup"><span data-stu-id="4816a-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="4816a-117">場所ポリシーを会議用に構成した場合、E9-1-1 サービス プロバイダーでも会議機能がサポートされているときは、社内のセキュリティ デスクが一方向音声または双方向の音声で通話に参加します。</span><span class="sxs-lookup"><span data-stu-id="4816a-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="4816a-118">通話が途中で終了した場合、PSAP はコールバック番号を使用して発信者に直接連絡します。</span><span class="sxs-lookup"><span data-stu-id="4816a-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

