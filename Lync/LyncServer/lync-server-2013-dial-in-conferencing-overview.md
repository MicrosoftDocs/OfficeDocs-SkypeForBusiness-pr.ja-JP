---
title: Lync Server 2013 ダイヤルイン会議の概要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d088d07e5d49a916835da581af81ff7def581b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="dd9ed-102">Lync Server 2013 でのダイヤルイン会議の概要</span><span class="sxs-lookup"><span data-stu-id="dd9ed-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd9ed-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="dd9ed-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="dd9ed-104">不在時に、またはコンピューターにアクセスできない Lync Server 2013 オンプレミスの会議に出席する必要があるユーザーが組織に存在する場合は、ダイヤルイン会議を展開して、公衆交換電話を使用して会議に参加できるようにすることができます。ネットワーク (PSTN) 電話</span><span class="sxs-lookup"><span data-stu-id="dd9ed-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="dd9ed-105">ダイヤルイン会議は、Lync Server 2013 会議を展開するときに構成できるオプションの機能です。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="dd9ed-106">ダイヤルイン会議では、エンタープライズ Voip で使用されているものと同じ Lync Server 2013 コンポーネントの一部を使用していますが、エンタープライズ Voip を展開しない場合でも、ダイヤルイン会議を展開できます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd9ed-107">ダイヤルイン会議を展開する場合は、Lync Server 2013 会議を展開するすべてのプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="dd9ed-108">すべてのプールでアクセス番号を割り当てる必要はありませんが、すべてのプールにダイヤルイン機能を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="dd9ed-109">この要件では、ユーザーが1つのプールのアクセス番号を呼び出して Lync Server 2013 会議を別のプールに参加させるときに、記録された名前の機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="dd9ed-110">会議ポリシーのダイヤルインアクセスでは、会議を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="dd9ed-111">既定では、ダイヤルインアクセスが有効になっている会議には、会議出席依頼に次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="dd9ed-112">電話会議を識別する数値電話会議 ID。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="dd9ed-113">1つ以上の PSTN アクセス番号。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="dd9ed-114">ダイヤルイン会議の設定ページへのリンク。関連付けられている言語と共にアクセス番号の完全なリストが含まれています。個人識別番号 (Pin) の作成、リセット、またはブロック解除を行う場所。その他の情報 (デュアルトーン多重周波数 (DTMF) コントロールなど)。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="dd9ed-115">ダイヤルイン会議では、エンタープライズユーザーと匿名ユーザーの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="dd9ed-116">エンタープライズユーザーは、組織内に Active Directory ドメインサービスの資格情報と Lync Server 2013 のアカウントを持っています。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="dd9ed-117">匿名ユーザーは、組織内にエンタープライズ資格情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="dd9ed-118">ダイヤルイン会議のコンテキストで、PSTN を使用して会議に接続するフェデレーションパートナーの組織内のユーザーは、匿名ユーザーと同様に扱われます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="dd9ed-119">ダイヤルイン会議では、他のコンテキストとは異なり、フェデレーションユーザーは認証されません。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="dd9ed-120">ダイヤルインアクセスが有効になっている会議に参加しているエンタープライズユーザーまたは電話会議リーダーは、電話会議のアクセス番号のいずれかをダイヤルし、会議 ID の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="dd9ed-121">リーダーが会議に参加していない場合、ユーザーは自分の統合コミュニケーション (UC) 内線番号 (または完全な電話番号) と PIN を入力するか、またはリーダーが許可されるまで待機することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="dd9ed-122">会議の開催者は、自分の PIN のみを入力して、会議にリーダーとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="dd9ed-123">フロントエンドサーバーは、エンタープライズユーザーを Active Directory 資格情報に一意にマップするために、完全な電話番号または内線番号と PIN の組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="dd9ed-124">その結果、エンタープライズユーザーが認証され、会議の名前によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="dd9ed-125">エンタープライズユーザーも、開催者によって事前定義された会議の役割を引き受けることができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd9ed-126">Office IP 電話からダイヤルインするエンタープライズユーザー、または Lync Server 2013 または Lync 2010 アテンダントは、既に認証されているため、電話番号の入力を求められません。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="dd9ed-127">匿名ユーザーがダイヤルイン会議に参加しようとすると、電話会議のアクセス番号のいずれかをダイヤルし、会議 ID の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-127">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID.</span></span> <span data-ttu-id="dd9ed-128">認証されていない匿名ユーザーも、名前を記録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-128">Unauthenticated anonymous users are also prompted to record their name.</span></span> <span data-ttu-id="dd9ed-129">記録された名前は、電話会議で認証されていないユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-129">The recorded name identifies unauthenticated users in the conference.</span></span> <span data-ttu-id="dd9ed-130">匿名ユーザーは、少なくとも1人のリーダーまたは認証されたユーザーが参加していて、定義済みの役割を割り当てられない限り、会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-130">Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd9ed-131">電話番号と PIN を入力しないエンタープライズユーザーは認証されません。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-131">Enterprise users who choose not to enter their phone number and PIN are not authenticated.</span></span> <span data-ttu-id="dd9ed-132">これらのユーザーは、名前を記録するように求められ、会議で匿名ユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-132">They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="dd9ed-133">スケジュールされた時間に、会議の開催者は会議を閉じるか、または、ロックすることによって、会議へのアクセスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="dd9ed-134">この場合、ダイヤルインユーザーは認証を要求されます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="dd9ed-135">ダイヤルインユーザーが失敗するか、認証しないことを選択すると、そのユーザーはロビーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="dd9ed-136">リーダーが許可または拒否するか、タイムアウトになって切断されるまで、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="dd9ed-137">ダイヤルインユーザーが会議への参加を待機している場合は、音楽を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="dd9ed-138">電話会議に参加した後は、電話のキーパッドを使用して、ダイヤルインユーザーが会議の音声部分に参加し、デュアルトーン多重周波数 (DTMF) コマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="dd9ed-139">ダイヤルインリーダーは、DTMF コマンドを実行して、参加者のミュートのオン/オフの切り替え、会議のロックまたはロック解除、ロビーからの参加者の許可、オン/オフの切り替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="dd9ed-140">また、リーダーは、DTMF コマンドを使用して、ロビーからのすべてのユーザーを許可することができます。これにより、会議のアクセス許可が変更され、後から参加するすべてのユーザーが参加できるように</span><span class="sxs-lookup"><span data-stu-id="dd9ed-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="dd9ed-141">すべてのダイヤルイン参加者は、DTMF コマンドを使用して、ヘルプを聞いたり、会議名簿を聞いたり、自分をミュートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="dd9ed-142">ダイヤルイン参加者 (PSTN からダイヤルするかどうかに関係なく) には、電話会議中に、ミュートまたはミュート解除であるか、会議が記録されているか、または他のユーザーがロビーで待機しているかどうかなどの個人アナウンスが音声で流れます。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd9ed-143">ダイヤルインではなくリンクをクリックして会議に参加する参加者には、個人的なアナウンスは音声で通知されません。</span><span class="sxs-lookup"><span data-stu-id="dd9ed-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

