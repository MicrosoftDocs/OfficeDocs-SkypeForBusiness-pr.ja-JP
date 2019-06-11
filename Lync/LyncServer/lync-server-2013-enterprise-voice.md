---
title: 'Lync Server 2013: エンタープライズ VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="05d5c-102">Lync Server 2013 のエンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="05d5c-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05d5c-103">_**最終更新日:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="05d5c-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="05d5c-104">エンタープライズ Voip では、Lync Server は、従来の構内交換 (PBX) システムを強化または交換するための、スタンドアロンのボイスオーバーインターネットプロトコル (VoIP) サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="05d5c-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="05d5c-105">エンタープライズボイスユーザーは、組織の VoIP ネットワークまたは PBX で同僚に通話を発信したり、組織外の従来の電話番号に通話したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="05d5c-106">エンタープライズ Voip ソリューションには、回答、forward、transfer、hold、転送すれば、release、パークなどの一般的な通話機能、強化された 9-1-1 (E9) 通話 (E9 は米国でのみ利用可能) が含まれています。エンタープライズボイスは、さまざまな現在および古い IP デバイスと USB デバイスもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="05d5c-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="05d5c-107">通話の発信と受信</span><span class="sxs-lookup"><span data-stu-id="05d5c-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="05d5c-108">Lync を使用すると、ユーザーはキーボードで名前または電話番号を入力したり、画面に表示されているダイヤルパッドを使って通話を発信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="05d5c-109">ユーザーは、連絡先リストから直接通話を開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="05d5c-110">また、Microsoft パートナーによって提供されるスタンドアロンの IP 電話デバイスである Lync Phone Edition デバイスを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="05d5c-111">ユーザーは、複数の電話デバイスを Lync Server に登録して、簡単に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="05d5c-112">ユーザーには、すべてのデバイスで同時に着信があった場合に、IP 電話デバイスのカスタマイズ可能な着信音、および PC でのインスタントメッセージに似た通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="05d5c-113">また、ユーザーは、自分の机の電話、PC、携帯電話に接続する1つの電話番号を設定して、どこにいても連絡できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="05d5c-114">基本的な通話機能</span><span class="sxs-lookup"><span data-stu-id="05d5c-114">Basic Call Features</span></span>

<span data-ttu-id="05d5c-115">通話中に、ユーザーは追加の着信通話に応答したり、発信通話を開始したりできます。また、既存のアクティブな通話が自動的に保留になります。</span><span class="sxs-lookup"><span data-stu-id="05d5c-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="05d5c-116">通話は、直接、または最初のユーザーが2番目のユーザーとプライベートに話すと、別のユーザーに転送できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="05d5c-117">また、ユーザーは通話を別のデバイスに転送することもできます。たとえば、office のドアを見ながら、アクティブな通話を携帯電話に転送することができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="05d5c-118">より充実したコミュニケーション</span><span class="sxs-lookup"><span data-stu-id="05d5c-118">Richer Communications</span></span>

<span data-ttu-id="05d5c-119">Lync を使用して別のユーザーと話すときに、ユーザーはテキスト、ビデオ、またはデスクトップの共有を簡単に通話に追加できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="05d5c-120">[応答不可] 機能は、Lync のプレゼンス設定と統合されています。</span><span class="sxs-lookup"><span data-stu-id="05d5c-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="05d5c-121">Exchange ユニファイドメッセージング (UM)、Lync、Lync Server を Microsoft Exchange Server 2013 および Microsoft Outlook 2013 と統合します。</span><span class="sxs-lookup"><span data-stu-id="05d5c-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="05d5c-122">ユーザーは、Lync ウィンドウとメールの両方で、新しいボイスメールがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="05d5c-123">メールでは、クリックしてメールメッセージでボイスメールの音声を再生したり、ボイスメールメッセージのトランスクリプトを表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="05d5c-124">高度な通話機能</span><span class="sxs-lookup"><span data-stu-id="05d5c-124">Advanced Calling Features</span></span>

<span data-ttu-id="05d5c-125">エンタープライズボイスには、Lync 通話の委任、チーム呼び出し、グループ通話のピックアップ、応答グループなど、高度な通話機能もいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="05d5c-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="05d5c-126">Lync 通話の委任を使用すると、ユーザーは [**ツール** \> **]** \>の [着信の**転送設定**] に移動して、1人または複数のアシスタントに通話処理を委任することができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="05d5c-127">代理人は、ユーザーに代わって複数の通話タスクを実行できます。これには、通話のスクリーニング、通話の発信、会議の開始などがあります。</span><span class="sxs-lookup"><span data-stu-id="05d5c-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="05d5c-128">同じような名前の付いた Lync 予定表の代理人を探している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05d5c-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="05d5c-129">エンタープライズ Voip 機能は不要であり、ユーザーは Outlook からのオンライン Lync 会議のスケジュールを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="05d5c-130">この情報を探していた場合は、Exchange 委任の同期を有効にする方法については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> 」を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05d5c-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="05d5c-131">チーム呼び出しを使用すると、ユーザーは、チームメンバーが着信に応答できるように、参加者の電話を同時に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="05d5c-132">グループ通話のピックアップ (Lync Server 2013 の累積更新プログラムの新機能: 2013 年2月) では、ユーザーは自分の電話から同僚への着信に応答できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="05d5c-133">グループ通話の集配は、主に、目的の受信者の電話でのみ着信が発生するという点で、チーム呼び出しとは異なります。ただし、他のユーザーは、通話ピックアップグループ番号にダイヤルすることによって応答することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="05d5c-134">応答グループは、指定したエージェントへの通話をキューに入れ、インテリジェントにルーティングするように設定できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="05d5c-135">一般的な用途としては、ヘルプデスク、人的リソースホットライン、その他の社内連絡先センターがあります。</span><span class="sxs-lookup"><span data-stu-id="05d5c-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="05d5c-136">エンタープライズボイス管理</span><span class="sxs-lookup"><span data-stu-id="05d5c-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="05d5c-137">Lync Server は、標準および公開されたインターフェイスを使って、既存のインフラストラクチャと相互運用します。</span><span class="sxs-lookup"><span data-stu-id="05d5c-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="05d5c-138">この機能は、IP PBX システムと PSTN ネットワークとの間のゲートウェイと SIP の両方のオプション (SIP トランキングなど) をサポートしているので、中断を最小限に抑えながら、ユーザーをエンタープライズ Voip に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="05d5c-139">Lync Server は、722、723.1 などの従来のコーデックをサポートしており、従来の VoIP ソリューションとの相互運用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="05d5c-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="05d5c-140">通話受付制御 (CAC) では、管理者は、制限付きのネットワークリンクで伝送される Lync Server の音声とビデオのトラフィックの量に制限を設定し、新しい通話が制限を超えた場合に実行する操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="05d5c-141">アクションには、代替パスによるルーティング、または通話の拒否を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="05d5c-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="05d5c-142">Lync Server は、サードパーティの Survivable ブランチアプライアンスと連携して、中央サイトで WAN 障害が発生した場合に、支店の PSTN へのローカル通話サービスと接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="05d5c-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

