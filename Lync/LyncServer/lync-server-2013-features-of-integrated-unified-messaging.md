---
title: 'Lync Server 2013: 統合ユニファイド メッセージングの機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5dc6396bd78977d099e650f14ae1a0b4b46c54e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="ed267-102">統合ユニファイド メッセージングと Lync Server 2013 の機能</span><span class="sxs-lookup"><span data-stu-id="ed267-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed267-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ed267-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ed267-104">Lync Server 2013 のエンタープライズボイスは、Exchange ユニファイドメッセージング (UM) インフラストラクチャを使用して、通話応答、通話の通知、音声アクセス (ボイスメールを含む)、自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ed267-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="ed267-105">通話応答</span><span class="sxs-lookup"><span data-stu-id="ed267-105">Call Answering</span></span>

<span data-ttu-id="ed267-106">通話応答は、通話に応答しない、または取り込み中であるユーザーの代わりに音声メッセージを受信することです。</span><span class="sxs-lookup"><span data-stu-id="ed267-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="ed267-107">これには、個人的な応答メッセージの再生、メッセージの記録、およびユーザーのメールボックスへの配信のためのキューに登録されるメッセージを送信することが含まれます。これは、Exchange メールボックスサーバーに保存されています。</span><span class="sxs-lookup"><span data-stu-id="ed267-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="ed267-p102">発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed267-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="ed267-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="ed267-112">Outlook Voice Access</span></span>

<span data-ttu-id="ed267-113">Outlook Voice Access を使うと、エンタープライズボイスユーザーは、ボイスメールだけでなく、テレフォニーインターフェイスのメール、予定表、連絡先などの Exchange の受信トレイにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed267-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="ed267-114">サブスクライバーのアクセス番号は、Exchange UM 管理者によって割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ed267-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="ed267-115">自動応答</span><span class="sxs-lookup"><span data-stu-id="ed267-115">Auto Attendant</span></span>

<span data-ttu-id="ed267-116">自動応答は、外部のユーザーが会社の代表者に連絡するためにダイヤルできる電話番号を構成するために使用できる Exchange UM の機能です。</span><span class="sxs-lookup"><span data-stu-id="ed267-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="ed267-117">特に、外部の発信者によるメニューシステムの移動を支援する一連の音声プロンプトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ed267-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="ed267-118">使用できるオプションの一覧は、exchange um 管理者によって Exchange UM サーバー上で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ed267-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="ed267-119">Fax サービス</span><span class="sxs-lookup"><span data-stu-id="ed267-119">Fax Services</span></span>

<span data-ttu-id="ed267-120">Exchange UM には fax 機能が含まれています。これにより、ユーザーは Exchange メールボックスで着信 fax を受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ed267-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="ed267-121">詳細については、Microsoft Exchange Server のドキュメントの「ユニファイド[http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)メッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed267-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed267-122">Exchange UM サーバーによって提供される Fax サービスは、Microsoft Exchange Server 2010 2010 に統合された Lync Server 展開、および最新の service pack または Exchange 2013 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="ed267-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

