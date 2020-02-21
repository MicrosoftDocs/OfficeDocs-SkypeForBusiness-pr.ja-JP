---
title: Lync Server 2013 エンタープライズ Voip
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="78d29-102">Lync Server 2013 のエンタープライズ Voip</span><span class="sxs-lookup"><span data-stu-id="78d29-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d29-103">_**トピックの最終更新日:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="78d29-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="78d29-104">エンタープライズ Voip では、Lync Server は、従来の構内交換 (PBX) システムを拡張または置換するためのスタンドアロンボイスオーバーインターネットプロトコル (VoIP) を提供します。</span><span class="sxs-lookup"><span data-stu-id="78d29-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="78d29-105">エンタープライズ VoIP ユーザーは、組織の VoIP ネットワークまたは PBX で仕事仲間を呼び出し、組織外の従来の電話番号を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="78d29-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="78d29-106">エンタープライズ Voip ソリューションには、answer、forward、transfer、hold、divert、release and パーク、Enhanced 9-1-1 (E9-1-1) 通話などの一般的な通話機能が含まれています (E9-1-1) (米国でのみ使用可能)。エンタープライズ Voip では、広範な現在および古い IP デバイスと USB デバイスもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="78d29-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="78d29-107">通話の発信と着信</span><span class="sxs-lookup"><span data-stu-id="78d29-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="78d29-108">Lync を使用すると、ユーザーは自分のキーボードで名前または電話番号を入力するか、画面に表示されているダイヤルパッドを使用して通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="78d29-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="78d29-109">ユーザーは、連絡先一覧から直接通話を開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="78d29-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="78d29-110">また、Microsoft パートナーによって提供されるスタンドアロンの IP 電話デバイスである、Lync Phone Edition デバイスを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="78d29-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="78d29-111">ユーザーは、Lync Server に登録されている複数の電話デバイスを使用して、それらを簡単に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="78d29-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="78d29-112">ユーザーは、自分のすべてのデバイスで同時に通話の着信を知らされます。IP 電話機ではカスタマイズが可能な着信音、PC ではインスタント メッセージに類似の通知が使用されます。</span><span class="sxs-lookup"><span data-stu-id="78d29-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="78d29-113">また、ユーザーは卓上電話、PC、携帯電話に接続する電話番号を 1 つに設定できるため、どこにいても連絡を受けられます。</span><span class="sxs-lookup"><span data-stu-id="78d29-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="78d29-114">基本的な通話機能</span><span class="sxs-lookup"><span data-stu-id="78d29-114">Basic Call Features</span></span>

<span data-ttu-id="78d29-p103">通話中、ユーザーは別の着信通話に応答したり発信通話を開始したりできます。その間、既存のアクティブな通話は自動的に保留されます。 通話は、あるユーザーから別のユーザーに直接転送するか、最初のユーザーが 2 番目のユーザーと個人的に話した後に転送できます。 ユーザーは通話を別のデバイスに転送することもできます。たとえば、オフィスの外に出るときに、アクティブな通話を携帯電話に転送できます。</span><span class="sxs-lookup"><span data-stu-id="78d29-p103">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold. Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user. Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="78d29-118">より高度な通信</span><span class="sxs-lookup"><span data-stu-id="78d29-118">Richer Communications</span></span>

<span data-ttu-id="78d29-119">Lync を使用して他のユーザーと話すときに、ユーザーはテキスト、ビデオ、またはデスクトップ共有を簡単に通話に追加できます。</span><span class="sxs-lookup"><span data-stu-id="78d29-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="78d29-120">"応答不可" 機能は、Lync のプレゼンス設定と統合されています。</span><span class="sxs-lookup"><span data-stu-id="78d29-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="78d29-121">Exchange ユニファイドメッセージング (UM)、Lync および Lync Server は、Microsoft Exchange Server 2013 および Microsoft Outlook 2013 と統合されています。</span><span class="sxs-lookup"><span data-stu-id="78d29-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="78d29-122">ユーザーは、Lync ウィンドウと電子メールの両方に新しいボイスメールがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="78d29-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="78d29-123">さらに電子メールでは、クリックして、電子メール メッセージ内のボイス メールの音声を再生したり、ボイス メール メッセージのトランスクリプトを表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="78d29-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="78d29-124">高度な通話機能</span><span class="sxs-lookup"><span data-stu-id="78d29-124">Advanced Calling Features</span></span>

<span data-ttu-id="78d29-125">エンタープライズ Voip には、Lync 通話の委任、チーム呼び出し、グループ通話ピックアップ、応答グループなど、いくつかの高度な通話機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="78d29-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="78d29-126">Lync 通話の委任を使用すると、[**ツール** \> **オプション]** \>の [着信**転送設定**] にアクセスして、ユーザーが1人または複数のアシスタントに通話処理を委任できるようになります。</span><span class="sxs-lookup"><span data-stu-id="78d29-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="78d29-127">委任されたスタッフは、ユーザーの代わりに、通話の選別、通話の発信、会議の開始などの複数の通話タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="78d29-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78d29-128">同じような名前の別の機能である Lync 予定表の委任を検索している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78d29-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="78d29-129">エンタープライズ Voip 機能を必要とせず、ユーザーが Outlook からオンラインで Lync 会議をスケジュールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="78d29-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="78d29-130">この情報を検索するには、「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> 」を参照して、Exchange 代理人の同期を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78d29-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="78d29-131">チーム呼び出しを使用すると、ユーザーは、チームの全員が通話に応答できるように、参加者の電話を同時に着信することができます。</span><span class="sxs-lookup"><span data-stu-id="78d29-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="78d29-132">グループ通話ピックアップ (Lync Server 2013 の累積的な更新プログラムの新機能: 2 月 2013) を使用すると、ユーザーは自分の電話から自分の仕事仲間への着信呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="78d29-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="78d29-133">グループ通話ピックアップは主に、目的の受信者の電話でのみ着信呼び出しが発信されるということですが、他のユーザーは通話ピックアップグループ番号をダイヤルすることによって応答することができます。</span><span class="sxs-lookup"><span data-stu-id="78d29-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="78d29-p109">応答グループは、キューイング、および呼び出し先エージェントへの通話の複雑なルーティングに対応するように設定できます。 一般的な使用法には、IT ヘルプデスク、人事部ホットライン、その他の社内コンタクト センターなどがあります。</span><span class="sxs-lookup"><span data-stu-id="78d29-p109">Response Groups can be set up for queuing and intelligently routing calls to designated agents. Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="78d29-136">エンタープライズ VoIP の管理</span><span class="sxs-lookup"><span data-stu-id="78d29-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="78d29-137">Lync Server は、標準と発行されたインターフェイスを使用して、既存のインフラストラクチャと相互運用します。</span><span class="sxs-lookup"><span data-stu-id="78d29-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="78d29-138">IP PBX システムおよび PSTN ネットワークへの相互接続用にゲートウェイと SIP オプション (SIP トランキングなど) の両方をサポートするため、混乱を最小限に抑えながら、時間をかけてユーザーをエンタープライズ VoIP に移行できます。</span><span class="sxs-lookup"><span data-stu-id="78d29-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="78d29-139">Lync Server は、従来の VoIP ソリューションとの相互運用性を実現するために、g.722、g.723.1 などの従来のコーデックをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="78d29-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="78d29-140">通話受付管理 (CAC) を使用すると、管理者は、制限されたネットワークリンクで実行される Lync Server の音声およびビデオのトラフィックの量に関する制限を設定したり、新しい呼び出しが制限を超えた場合に実行するアクションを指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="78d29-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="78d29-141">このアクションには、代替パスによるルーティングや、通話の拒否などがあります。</span><span class="sxs-lookup"><span data-stu-id="78d29-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="78d29-142">Lync Server は、サードパーティ製の存続可能ブランチアプライアンスと連携して、中央サイトで WAN 障害が発生した場合に、ローカルの通話サービスを提供し、支店で PSTN に接続します。</span><span class="sxs-lookup"><span data-stu-id="78d29-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

