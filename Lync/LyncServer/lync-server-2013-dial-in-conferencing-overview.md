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
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="374dc-102">Lync Server 2013 でのダイヤルイン会議の概要</span><span class="sxs-lookup"><span data-stu-id="374dc-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="374dc-103">_**最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="374dc-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="374dc-104">組織で Lync Server 2013 オンプレミス会議に参加する必要があるユーザーが不在時またはコンピューターへのアクセス権を持っていない場合は、ダイヤルイン会議を展開して、公衆交換電話を使って会議に参加できるようにすることができます。ネットワーク (PSTN) 電話。</span><span class="sxs-lookup"><span data-stu-id="374dc-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="374dc-105">ダイヤルイン会議は、Lync Server 2013 会議の展開時に構成できるオプションの機能です。</span><span class="sxs-lookup"><span data-stu-id="374dc-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="374dc-106">ダイヤルイン会議ではエンタープライズボイスで使用されるものと同じ Lync Server 2013 コンポーネントの一部が使用されていますが、エンタープライズ Voip を展開していない場合でも、ダイヤルイン会議を展開できます。</span><span class="sxs-lookup"><span data-stu-id="374dc-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="374dc-107">ダイヤルイン会議を展開する場合は、Lync Server 2013 会議を展開するすべてのプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="374dc-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="374dc-108">すべてのプールにアクセス番号を割り当てる必要はありませんが、すべてのプールにダイヤルイン機能を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="374dc-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="374dc-109">この要件では、ユーザーが1つのプールのアクセス番号を呼び出して Lync Server 2013 会議に別のプールで参加した場合に、記録された名前の機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="374dc-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="374dc-110">会議ポリシーのダイヤルインアクセスでは、会議を有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="374dc-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="374dc-111">既定では、会議でダイヤルイン アクセスが有効になっている場合は、会議の招待通知に次の情報が記載されます。</span><span class="sxs-lookup"><span data-stu-id="374dc-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="374dc-112">電話会議を識別する数値の会議 ID。</span><span class="sxs-lookup"><span data-stu-id="374dc-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="374dc-113">1つ以上の PSTN アクセス番号。</span><span class="sxs-lookup"><span data-stu-id="374dc-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="374dc-114">[ダイヤルイン会議の設定] ページへのリンク。関連付けられている言語と共に、アクセス番号の完全な一覧が含まれています。暗証番号 (Pin) を作成、リセット、またはブロック解除する場所。その他の情報 (デュアルトーンマルチ周波数 (DTMF) コントロールなど)。</span><span class="sxs-lookup"><span data-stu-id="374dc-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="374dc-115">ダイヤルイン会議は、エンタープライズ ユーザーと匿名ユーザーの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="374dc-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="374dc-116">エンタープライズユーザーには、組織内で Active Directory ドメインサービスの資格情報と Lync Server 2013 アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="374dc-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="374dc-117">匿名ユーザーは、組織内のエンタープライズ資格情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="374dc-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="374dc-118">ダイヤルイン会議では、フェデレーション パートナーの組織で PSTN を使用して会議に電話接続するユーザーは、匿名ユーザーのように扱われます。</span><span class="sxs-lookup"><span data-stu-id="374dc-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="374dc-119">ダイヤルイン会議では、他の状況とは異なり、フェデレーション ユーザーは認証されません。</span><span class="sxs-lookup"><span data-stu-id="374dc-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="374dc-p105">ダイヤルイン アクセスが有効な会議に参加するエンタープライズ ユーザーまたは会議主催者は、電話会議のアクセス番号の 1 つをダイヤルすると、電話会議 ID を入力するよう求められます。会議主催者が会議にまだ参加していない場合、ユーザーは、統合コミュニケーション (UC) 内線番号 (または完全な電話番号) と PIN を入力するか、会議主催者によって許可されるまで待機できます。会議の開催者は、PIN を入力するだけで、主催者として会議に参加できます。フロントエンド サーバーでは、完全な電話番号または内線番号と PIN の組み合わせを使用して、エンタープライズ ユーザーを Active Directory の資格情報に一意にマップします。これによって、エンタープライズ ユーザーは認証を受けて、電話会議では名前で識別されます。また、エンタープライズ ユーザーは、開催者が事前に定義した電話会議の役割を引き受けることもできます。</span><span class="sxs-lookup"><span data-stu-id="374dc-p105">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="374dc-126">Office IP 電話からダイヤルインするか、Lync Server 2013 または Lync 2010 アテンダントからダイヤルインするエンタープライズユーザーは、既に認証されているため、電話番号を入力するように求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="374dc-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="374dc-p106">ダイヤルイン電話会議に参加する必要がある匿名ユーザーは、電話会議のアクセス番号の 1 つをダイヤルすると、電話会議 ID を入力するよう求められます。認証されていない匿名ユーザーは、名前を録音するようにも求められます。会議に出席中の認証されていないユーザーは、この録音された名前によって識別されます。 少なくとも 1 人の主催者または認証済みのユーザーが参加するまで、匿名ユーザーは会議への参加が許可されません。また、匿名ユーザーには事前に定義された役割は割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="374dc-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="374dc-p107">電話番号と PIN を入力しないエンタープライズ ユーザーは認証されません。そのようなユーザーは名前を録音するよう求められ、電話会議で匿名ユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="374dc-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="374dc-133">スケジュールされた時間で、会議の開催者は、会議を閉じるか、またはロックして会議へのアクセスを制限することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="374dc-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="374dc-134">この場合、ダイヤルイン ユーザーは認証が要求されます。</span><span class="sxs-lookup"><span data-stu-id="374dc-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="374dc-135">ダイヤルインユーザーが失敗するか、認証しないことを選択すると、そのユーザーはロビーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="374dc-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="374dc-136">ロビー内で待機するのは、リーダーが承諾または拒否したとき、またはタイムアウトして切断されたときです。</span><span class="sxs-lookup"><span data-stu-id="374dc-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="374dc-137">ダイヤルインユーザーは、会議への参加を待機している場合、音楽を聞きます。</span><span class="sxs-lookup"><span data-stu-id="374dc-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="374dc-138">会議への参加が許可されると、ダイヤルイン ユーザーは会議の音声部分に参加し、電話キーパッドを使用して、デュアルトーン多重周波数 (DTMF) コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="374dc-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="374dc-139">ダイヤルイン会議の主催者は、DTMF コマンドを実行して参加者のミュート解除機能のオンとオフの切り替え、会議のロックとロック解除、ロビーからのユーザーの許可、および入室と退室のアナウンスのオンとオフの切り替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="374dc-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="374dc-140">また、主催者は、DTMF コマンドを使用してロビーからのすべてのユーザーを許可できるため、後から参加するすべてのユーザーを許可するよう、会議のアクセス許可が変更されます。</span><span class="sxs-lookup"><span data-stu-id="374dc-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="374dc-141">すべてのダイヤルイン参加者は、DTMF コマンドを実行して、ヘルプを聞いたり、会議名簿を聞いたり、自分をミュートにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="374dc-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="374dc-142">ダイヤルイン参加者 (つまり、PSTN からダイヤルしているかどうかに関係なく) は、電話会議中にミュートがミュートになっているか、されているか、会議が記録中であるか、または他のユーザーがロビーで待機しているかどうかなど、会議中に個人的なお知らせを聞きます。</span><span class="sxs-lookup"><span data-stu-id="374dc-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="374dc-143">ダイヤルインではなくリンクをクリックして会議に参加する参加者には、個人向けアナウンスは流されません。</span><span class="sxs-lookup"><span data-stu-id="374dc-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

