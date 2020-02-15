---
title: 'Lync Server 2013: リモート通話コントロールの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="e3cf2-102">Lync Server 2013 でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="e3cf2-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3cf2-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="e3cf2-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="e3cf2-104">Lync Server 2013 では、リモート通話コントロールシナリオのサポートにより、ユーザーは自分のデスクトップコンピューター上で Lync 2013 を使用して、構内交換機 (PBX) 電話を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="e3cf2-105">このセクションでは、リモート通話コントロール機能およびリモート通話コントロールを展開するための要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="e3cf2-106">PBX と Lync Server 2013 との統合により、リモート通話コントロールが有効になっているユーザーは、次の方法で Lync 2013 ユーザーインターフェイス (UI) を使用して PBX 電話機の呼び出しを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3cf2-107">最終的には、ユーザーの PBX 電話をホストする PBX の機能が、そのユーザーが利用することができるリモート通話コントロールの機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="e3cf2-108">通話を発信する</span><span class="sxs-lookup"><span data-stu-id="e3cf2-108">Make an outgoing call</span></span>

  - <span data-ttu-id="e3cf2-109">着信通話に応答する</span><span class="sxs-lookup"><span data-stu-id="e3cf2-109">Answer an incoming call</span></span>

  - <span data-ttu-id="e3cf2-110">インスタント メッセージで着信した通話に応答する</span><span class="sxs-lookup"><span data-stu-id="e3cf2-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3cf2-111">つまり、発信者の電話番号は、組織のグローバルアドレス一覧 (GAL)、呼び出し先の Lync 連絡先リスト、またはフェデレーションパートナーの組織のインスタントメッセージアドレスに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="e3cf2-112">通話の転送</span><span class="sxs-lookup"><span data-stu-id="e3cf2-112">Transfer a call</span></span>

  - <span data-ttu-id="e3cf2-113">着信の転送</span><span class="sxs-lookup"><span data-stu-id="e3cf2-113">Forward an incoming call</span></span>

  - <span data-ttu-id="e3cf2-114">通話の保留</span><span class="sxs-lookup"><span data-stu-id="e3cf2-114">Place calls on hold</span></span>

  - <span data-ttu-id="e3cf2-115">複数の同時通話間の切り替え</span><span class="sxs-lookup"><span data-stu-id="e3cf2-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="e3cf2-116">すでに通話中である時に 2 番目の通話に応答する (つまり、通話中の着信)</span><span class="sxs-lookup"><span data-stu-id="e3cf2-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="e3cf2-117">デュアルトーン多重周波数 (DTMF) 電話番号をダイヤルする</span><span class="sxs-lookup"><span data-stu-id="e3cf2-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="e3cf2-118">[会話] ウィンドウで、Microsoft Office OneNote メモ プログラムにメモを入力する</span><span class="sxs-lookup"><span data-stu-id="e3cf2-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="e3cf2-119">さらに、ユーザーのリモート通話コントロールが有効になっている場合、Lync 2013 は次の呼び出し情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="e3cf2-120">呼び出し元の電話番号が、リモート通話コントロールが有効なユーザーの Microsoft Office Outlook メッセージングおよびコラボレーションクライアント、Lync 連絡先リスト、または組織の GAL の連絡先リストに存在する場合の、名前による発信者の id。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="e3cf2-121">Outlook の [会話履歴] フォルダーに保存されている、過去の着信および発信通話。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="e3cf2-122">不在着信通知は、ユーザーの Outlook 受信トレイフォルダーに送信されますが、着信呼び出しの受信時に Lync が実行されている場合にのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="e3cf2-123">リモート通話コントロールとエンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="e3cf2-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="e3cf2-124">リモート通話コントロール機能はエンタープライズ Voip 機能とは分離されていますが、両方のユーザーが有効にすることはできませんが、エンタープライズ Voip では、リモート通話コントロールが有効になっているユーザーも使用できる機能のサブセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="e3cf2-125">エンタープライズ Voip が展開されている場合、リモート通話コントロールが有効になっているユーザーは、Lync を使用して次のエンタープライズ Voip 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e3cf2-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="e3cf2-126">別の Lync クライアントに対する音声通話の作成と受信</span><span class="sxs-lookup"><span data-stu-id="e3cf2-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="e3cf2-127">エンタープライズ Voip が有効になっているユーザーが作成した会議のオーディオ部分に参加する</span><span class="sxs-lookup"><span data-stu-id="e3cf2-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3cf2-128">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e3cf2-128">In This Section</span></span>

  - [<span data-ttu-id="e3cf2-129">Lync Server 2013 でのリモート通話コントロールの展開タスク</span><span class="sxs-lookup"><span data-stu-id="e3cf2-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

