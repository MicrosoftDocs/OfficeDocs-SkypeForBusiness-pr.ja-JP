---
title: 'Lync Server 2013: 統合されたユニファイドメッセージングの機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c70df997e0ed42f77451287cccbae23ae93d14e6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="e4998-102">統合ユニファイドメッセージングと Lync Server 2013 の機能</span><span class="sxs-lookup"><span data-stu-id="e4998-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4998-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e4998-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e4998-104">Lync Server 2013、エンタープライズ Voip は、Exchange ユニファイドメッセージング (UM) インフラストラクチャを使用して、通話応答、通話通知、音声アクセス (ボイスメールを含む)、および自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4998-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="e4998-105">通話応答</span><span class="sxs-lookup"><span data-stu-id="e4998-105">Call Answering</span></span>

<span data-ttu-id="e4998-106">通話応答は、呼び出しに応答しない、または通話中であるユーザーの代わりに音声メッセージを受信することです。</span><span class="sxs-lookup"><span data-stu-id="e4998-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="e4998-107">これには、個人の案内応答の再生、メッセージの録音、およびメッセージを送信して、Exchange メールボックスサーバーに格納されているユーザーのメールボックスへの配信のためにキューに入れます。</span><span class="sxs-lookup"><span data-stu-id="e4998-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="e4998-p102">発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e4998-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="e4998-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="e4998-112">Outlook Voice Access</span></span>

<span data-ttu-id="e4998-113">Outlook Voice Access を使用すると、エンタープライズ VoIP ユーザーはボイス メールだけでなく、電子メール、予定表、およびテレフォニー インターフェイスの連絡先を含む Exchange 受信トレイにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e4998-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="e4998-114">サブスクライバーアクセス番号は、Exchange UM 管理者によって割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e4998-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="e4998-115">自動応答</span><span class="sxs-lookup"><span data-stu-id="e4998-115">Auto Attendant</span></span>

<span data-ttu-id="e4998-116">自動応答は、外部ユーザーが会社の代表者に到達するためにダイヤルする電話番号を構成するために使用できる Exchange UM の機能です。</span><span class="sxs-lookup"><span data-stu-id="e4998-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="e4998-117">具体的には、外部からの発信者に音声でメニュー システムの操作を案内します。</span><span class="sxs-lookup"><span data-stu-id="e4998-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="e4998-118">使用可能なオプションの一覧は、exchange UM 管理者によって Exchange UM サーバー上で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e4998-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="e4998-119">FAX サービス</span><span class="sxs-lookup"><span data-stu-id="e4998-119">Fax Services</span></span>

<span data-ttu-id="e4998-120">Exchange UM には fax 機能が含まれています。これにより、ユーザーは Exchange メールボックスで着信 fax を受信できます。</span><span class="sxs-lookup"><span data-stu-id="e4998-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="e4998-121">詳細については、Microsoft Exchange Server のドキュメントの「ユニファイド[http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)メッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4998-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4998-122">Exchange UM サーバーによって提供される Fax サービスは、Microsoft Exchange Server 2010、Exchange 2010、最新のサービスパック、または Exchange 2013 と統合されている Lync Server 展開では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e4998-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

