---
title: 'Lync Server 2013: 会議の移行に関する考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48ee24dca1cdf083de990ef42dae4017ed927e15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524564"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="8d670-102">Lync Server 2013 での会議の移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="8d670-102">Migration considerations for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d670-103">_**トピックの最終更新日:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="8d670-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="8d670-104">このセクションでは、次のトピックについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="8d670-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="8d670-105">Microsoft Lync Server 2013 での会議への変更</span><span class="sxs-lookup"><span data-stu-id="8d670-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="8d670-106">電話会議のニーズに基づくユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="8d670-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="8d670-107">既存の会議と会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="8d670-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="8d670-108">Lync Server 2010 の移行中のユーザーの作業</span><span class="sxs-lookup"><span data-stu-id="8d670-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="8d670-109">Office Communications Server 2007 R2 の移行中のユーザーの作業状況</span><span class="sxs-lookup"><span data-stu-id="8d670-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="8d670-110">Microsoft Lync 2013 の以前のサーバーバージョンの会議との互換性</span><span class="sxs-lookup"><span data-stu-id="8d670-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="8d670-111">Lync Server 2013 での会議の変更</span><span class="sxs-lookup"><span data-stu-id="8d670-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="8d670-112">**Lync Server 2013 の機能。**    Lync Server 2013 は、アカウントが Lync Server 2013 に移動され、Lync 2013 クライアントを使用してサインインした後で、ユーザーが利用できるようになる新しい会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d670-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="8d670-113">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md) 」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="8d670-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="8d670-114">**会議の URL。**    Lync Server 2010 と同様に、Lync Server 2013 で新しくスケジュールされた会議には、https://の URL プレフィックスがあり、既存の会議はユーザーアカウントと共に移行されます。</span><span class="sxs-lookup"><span data-stu-id="8d670-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="8d670-115">ただし、Lync Server 2013 は、Office Communications Server 2007 R2 会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8d670-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="8d670-116">詳細については、このトピックで後述する「Office Communications Server 2007 R2 からの会議の移行」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d670-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="8d670-117">**クライアントのサポート。**    Lync Server 2010 とは異なり、Lync Server 2013 は会議用の Office Communicator クライアントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8d670-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="8d670-118">次のクライアントを使用して、Lync 2013 用のオンライン会議アドインによってスケジュールされた会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d670-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="8d670-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8d670-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="8d670-120">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="8d670-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="8d670-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="8d670-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="8d670-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="8d670-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="8d670-123">移行時に、Office Communicator 2007 R2 ユーザーは Lync Web App 2013 を使用して、クライアントがアップグレードされるまで Lync Server 2013 会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d670-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="8d670-124">Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能に対して Lync Server 2013 に対して既存のクライアントを引き続き使用することができますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8d670-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="8d670-125">電話会議のニーズに基づくユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="8d670-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="8d670-126">**会議の開催者が頻繁に行われます。**    [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)と、 [lync 2013 server のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能について説明されている新しい Lync server 2013 および lync 2013 の機能を利用できるように、プロセスの早い段階で移行を行うことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8d670-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="8d670-127">**Live Meeting ユーザー。**    Office Communications Server 2007 R2 から移行していて、Live Meeting 固有の web 会議機能 (特に、大規模な会議およびブレイクアウトルームのサポート) を必要とするユーザーがいる場合は、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d670-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="8d670-128">組織で使用できる場合は、開催者に Live Meeting サービスを使用するように勧めます。</span><span class="sxs-lookup"><span data-stu-id="8d670-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="8d670-129">以前のバージョンの Office Communications Server に所属している開催者には、引き続きサーバーベースの Live Meeting web 会議のスケジュールを設定できるようにしておきます。</span><span class="sxs-lookup"><span data-stu-id="8d670-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="8d670-130">既存の会議と会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="8d670-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="8d670-131">Lync Server 2010 からの会議の移行</span><span class="sxs-lookup"><span data-stu-id="8d670-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="8d670-132">Lync Server 2010 から Lync Server 2013 にユーザーを移動すると、次の情報がユーザーのアカウントと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="8d670-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="8d670-133">そのユーザーがスケジュール済みの会議。</span><span class="sxs-lookup"><span data-stu-id="8d670-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="8d670-134">これには、会議ディレクトリと会議データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d670-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="8d670-135">ユーザーの暗証番号 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="8d670-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="8d670-136">ユーザーの現在の PIN は、有効期限が切れるか、またはユーザーが新しい PIN を要求するまでの間、引き続き有効です。</span><span class="sxs-lookup"><span data-stu-id="8d670-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="8d670-137">ただし、次のユーザーアカウント情報は新しいサーバーに移動しません。</span><span class="sxs-lookup"><span data-stu-id="8d670-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="8d670-138">会議コンテンツ (PowerPoint プレゼンテーション、ホワイトボードコンテンツ、投票データなど)</span><span class="sxs-lookup"><span data-stu-id="8d670-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="8d670-139">会議で共有されているコンテンツを移動するには、Move-CsUser コマンドレットの MoveMeetingContent パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d670-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="8d670-140">このコマンドレットの使用の詳細については、「Lync Server 2013 コマンドレット」のドキュメントの「 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d670-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="8d670-141">Office Communications Server 2007 R2 からの会議の移行</span><span class="sxs-lookup"><span data-stu-id="8d670-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="8d670-142">Office Communications Server 2007 R2 会議は、電話会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8d670-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="8d670-143">Lync Server 2013 では、これらの以前の conf://および meet://会議がサポートされておらず、ユーザーアカウントと共に移行されることもありません。</span><span class="sxs-lookup"><span data-stu-id="8d670-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="8d670-144">移行後に、スケジュールされたオンライン会議のリンクを更新するようにユーザーに指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d670-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="8d670-145">これは、Lync 2013 クライアントをインストールした後で、会議 URL を更新して参加者に招待状を再送信する予定の会議出席依頼を開くことによって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8d670-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="8d670-146">Lync Server 2010 の移行中のユーザーの作業</span><span class="sxs-lookup"><span data-stu-id="8d670-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="8d670-147">このセクションでは、Lync 2010 から移行する場合のユーザーの電話会議の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d670-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="8d670-148">Lync Server 2013 クライアントが以前のクライアントおよびサーバーバージョンと共存して操作する方法の詳細については、「 [lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d670-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="8d670-149">Lync Server 2010 会議の Lync 2013 クライアントへの参加</span><span class="sxs-lookup"><span data-stu-id="8d670-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="8d670-150">Lync Server 2010 からの移行中に、ユーザーが lync Server 2010 会議に Lync 2013 クライアントを参加させる場合、共存の期間が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8d670-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="8d670-151">これらのユーザーは、以下の例外を除き、Lync 2013 クライアント機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8d670-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="8d670-152">[ **参加者** の管理] オプションでは、会議ウィンドウの [ユーザー] アイコンをポイントすることによってアクセスできます。 [ **会議 IM** を利用しない] オプションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="8d670-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="8d670-153">ギャラリービューは、ビデオ会議では機能しません。</span><span class="sxs-lookup"><span data-stu-id="8d670-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="8d670-154">ユーザーには、すべてのスピーカーではなく、アクティブなスピーカーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d670-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="8d670-155">[レイアウトオプションの **選択** ] の一覧で、 **ギャラリービュー** を使用できません</span><span class="sxs-lookup"><span data-stu-id="8d670-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="8d670-156">参加者リストは、既定では、ビデオ会議に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d670-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="8d670-157">[参加者] リストでユーザーを右クリックすると、[ **ビデオスポットライトをロック** する] および [ギャラリー参加者管理 **にピン留めする** ] オプションが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8d670-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="8d670-158">Office Communications Server 2007 R2 の移行中のユーザーの作業状況</span><span class="sxs-lookup"><span data-stu-id="8d670-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="8d670-159">このセクションでは、Lync 2013 をインストールする前と後に、Office Communications Server 2007 R2 から移行する場合のユーザーの電話会議の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d670-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="8d670-160">Lync Server 2013 クライアントが以前のクライアントおよびサーバーバージョンと共存して操作する方法の詳細については、「 [lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d670-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="8d670-161">ユーザーアカウントが移行された後、Lync 2013 がインストールされる前</span><span class="sxs-lookup"><span data-stu-id="8d670-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="8d670-162">ユーザーが Lync Server 2013 サーバーに移行された後、新しいクライアントがインストールされる前に、Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能のために Lync Server 2013 に対して既存のクライアントを引き続き使用することができますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8d670-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="8d670-163">ユーザーアカウントが移行された後、Lync 2013 のインストール後</span><span class="sxs-lookup"><span data-stu-id="8d670-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="8d670-164">移行したユーザーが Lync 2013 をインストールすると、Lync 2013 用のオンラインミーティングアドインもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8d670-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="8d670-165">この場合、次の影響があります。</span><span class="sxs-lookup"><span data-stu-id="8d670-165">This has the following effects:</span></span>

  - <span data-ttu-id="8d670-166">今後予約する会議ではすべて、従来の会議形式の「meet:// Live Meeting アドレス」ではなく、新しい会議形式の「https:// アドレス」を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d670-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="8d670-167">Lync 2013 の IT 管理展開では、管理者は Live Meeting サーバーとサービスベースの会議のスケジュール設定に使用される Microsoft Office Outlook 用会議アドインをアンインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d670-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="8d670-168">ただし、Live Meeting サービス会議を引き続きスケジュールする必要があるユーザーがいる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d670-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="8d670-169">この場合、両方のアドインを共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="8d670-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="8d670-170">以前のクライアントを使用するフェデレーション組織との会議</span><span class="sxs-lookup"><span data-stu-id="8d670-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="8d670-171">会議が開催者によってロックされている場合、Microsoft Office Communicator 2007 を使用しているフェデレーション組織のユーザーは、組織内の Lync Server 2013 会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="8d670-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="8d670-172">フェデレーション参加者は、新しい https://会議 URL を使用して会議に参加するときに Lync Web App を使用できるように、Lync Server 2013 でこれらの会議をスケジュールし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d670-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

