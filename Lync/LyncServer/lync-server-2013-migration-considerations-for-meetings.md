---
title: 'Lync Server 2013: 会議の移行に関する考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67816dd8f2b9d8be3862994c735040c703bd2231
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="d4ef1-102">Lync Server 2013 での会議の移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d4ef1-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4ef1-103">_**最終更新日:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="d4ef1-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="d4ef1-104">このセクションでは、次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="d4ef1-105">Microsoft Lync Server 2013 での会議の変更点</span><span class="sxs-lookup"><span data-stu-id="d4ef1-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="d4ef1-106">会議のニーズに基づいてユーザーを移行する</span><span class="sxs-lookup"><span data-stu-id="d4ef1-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="d4ef1-107">既存の会議と会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="d4ef1-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="d4ef1-108">Lync Server 2010 の移行中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d4ef1-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="d4ef1-109">Office Communications Server 2007 R2 の移行中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d4ef1-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="d4ef1-110">Microsoft Lync 2013 以前のバージョンのサーバーの会議との互換性</span><span class="sxs-lookup"><span data-stu-id="d4ef1-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="d4ef1-111">Lync Server 2013 での会議の変更点</span><span class="sxs-lookup"><span data-stu-id="d4ef1-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="d4ef1-112">**Lync Server 2013 の機能。**   Lync server 2013 には、アカウントを lync server 2013 に移行した後でユーザーが利用できる新しい会議機能が用意されています。また、lync 2013 クライアントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="d4ef1-113">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d4ef1-114">**会議の URL。**   Lync server 2010 の場合と同様に、lync server 2013 で新しくスケジュールされた会議には、HTTPS://の URL プレフィックスと、既存の会議がユーザーアカウントと共に移行されます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="d4ef1-115">ただし、Lync Server 2013 は、Office Communications Server 2007 R2 会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="d4ef1-116">詳細については、このトピックの後半の「Office Communications Server 2007 R2 から会議を移行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="d4ef1-117">**クライアントのサポート。**   Lync server 2010 とは異なり、lync server 2013 では、会議用の Office Communicator クライアントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="d4ef1-118">Lync 2013 用のオンライン会議アドインによってスケジュールされた会議に、次のクライアントを使用して会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="d4ef1-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d4ef1-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="d4ef1-120">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="d4ef1-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="d4ef1-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="d4ef1-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="d4ef1-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d4ef1-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="d4ef1-123">Office Communicator 2007 R2 ユーザーは、移行中に Lync Web App 2013 を使って Lync Server 2013 会議に参加してから、顧客がアップグレードされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="d4ef1-124">Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能については、引き続き Lync Server 2013 に対して既存のクライアントを使用できますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="d4ef1-125">会議のニーズに基づいてユーザーを移行する</span><span class="sxs-lookup"><span data-stu-id="d4ef1-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="d4ef1-126">**会議の開催者の頻度。**    [Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)で示されている新しい Lync server 2013 および lync 2013 の機能を活用できるように、また、lync[のクライアントの新機能については、プロセスの早い段階で会議の開催者を頻繁に移行することを検討してください。サーバー 2013](lync-server-2013-what-s-new-for-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d4ef1-127">**Live Meeting ユーザー。**   Office Communications Server 2007 R2 から移行する場合、Live Meeting 固有の web 会議機能 (特に大規模な会議や休憩室のサポート) が必要なユーザーがいる場合は、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="d4ef1-128">組織で利用できる場合は、Live Meeting サービスを使用するように開催者に通知します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="d4ef1-129">サーバーベースの Live Meeting web 会議のスケジュールを維持できるように、以前のバージョンの Office Communications Server の開催者をホームにしておきます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="d4ef1-130">既存の会議と会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="d4ef1-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="d4ef1-131">Lync Server 2010 から会議を移行する</span><span class="sxs-lookup"><span data-stu-id="d4ef1-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="d4ef1-132">Lync Server 2010 から Lync Server 2013 にユーザーを移動すると、次の情報がユーザーのアカウントと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="d4ef1-133">ユーザーが既にスケジュールした会議。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="d4ef1-134">これには、会議ディレクトリと会議データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="d4ef1-135">ユーザーの暗証番号 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="d4ef1-136">ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="d4ef1-137">ただし、次のユーザーアカウント情報は新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="d4ef1-138">会議コンテンツ (PowerPoint プレゼンテーション、ホワイトボードコンテンツ、投票データなど)</span><span class="sxs-lookup"><span data-stu-id="d4ef1-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="d4ef1-139">会議で共有されているコンテンツを移動するには、移動-CsUser コマンドレットの MoveMeetingContent パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="d4ef1-140">このコマンドレットの使い方の詳細については、「Lync Server 2013 コマンドレットのドキュメントでの[移動-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="d4ef1-141">Office Communications Server 2007 R2 から会議を移行する</span><span class="sxs-lookup"><span data-stu-id="d4ef1-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="d4ef1-142">Office Communications Server 2007 R2 会議は、会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="d4ef1-143">Lync Server 2013 では、これらの以前の conf://と meet://の会議はサポートされておらず、ユーザーアカウントと共に移行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="d4ef1-144">移行後は、スケジュールしたオンライン会議のリンクを更新するようにユーザーに指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="d4ef1-145">この操作を行うには、スケジュールされた会議出席依頼を開き、会議の URL を更新し、参加者に招待状を再送信して、Lync 2013 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="d4ef1-146">Lync Server 2010 の移行中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d4ef1-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="d4ef1-147">このセクションでは、Lync 2010 から移行する場合のユーザーの会議エクスペリエンスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="d4ef1-148">Lync Server 2013 クライアントで、以前のクライアントとサーバーのバージョンを共存して操作する方法の詳細については、「 [lync 2013 でのクライアントの相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="d4ef1-149">Lync 2013 クライアントを使って Lync Server 2010 会議に参加する</span><span class="sxs-lookup"><span data-stu-id="d4ef1-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="d4ef1-150">Lync Server 2010 からの移行中に、ユーザーが lync 2013 クライアントを使って Lync Server 2010 会議に参加すると、共存期間が延長される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="d4ef1-151">これらのユーザーは、次の例外を除き、Lync 2013 クライアント機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="d4ef1-152">[会議] ウィンドウの [連絡先] アイコンをポイントしてアクセスできる**参加者**の管理オプションでは、[**会議 IM**を使わない] オプションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="d4ef1-153">ギャラリービューは、ビデオ会議では機能しません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="d4ef1-154">ユーザーは、すべてのスピーカーではなく、アクティブなスピーカーのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="d4ef1-155">[**レイアウトの選択**] オプションの一覧で、**ギャラリービュー**を使用できない</span><span class="sxs-lookup"><span data-stu-id="d4ef1-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="d4ef1-156">参加者リストは、ビデオ会議の既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="d4ef1-157">[参加者] リストでユーザーを右クリックすると、[**ビデオスポットライトをロック**する] と [**ギャラリーに参加するための Pin** ] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="d4ef1-158">Office Communications Server 2007 R2 の移行中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d4ef1-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="d4ef1-159">このセクションでは、Lync 2013 がインストールされている前と後の両方で、Office Communications Server 2007 R2 から移行するユーザーの会議エクスペリエンスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="d4ef1-160">Lync Server 2013 クライアントで、以前のクライアントとサーバーのバージョンを共存して操作する方法の詳細については、「 [lync 2013 でのクライアントの相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="d4ef1-161">ユーザーアカウントが移行された後、Lync 2013 がインストールされる前</span><span class="sxs-lookup"><span data-stu-id="d4ef1-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="d4ef1-162">ユーザーが Lync Server 2013 サーバーに移行された後、新しいクライアントがインストールされる前に、Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能のために、Lync Server 2013 に対して既存のクライアントを引き続き使用できますが、会議機能は使用できません。サポートされ.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="d4ef1-163">ユーザーアカウントが移行された後、Lync 2013 をインストールした後</span><span class="sxs-lookup"><span data-stu-id="d4ef1-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="d4ef1-164">移行したユーザーが Lync 2013 をインストールすると、Lync 2013 用のオンライン会議アドインもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="d4ef1-165">これには、次のような効果があります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-165">This has the following effects:</span></span>

  - <span data-ttu-id="d4ef1-166">以降のスケジュールされた会議では、新しい会議の形式が使用されます。これにより、従来の meet://Live Meeting のアドレスではなく、https://の住所が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="d4ef1-167">Lync 2013 の IT 管理展開では、管理者は Microsoft Office Outlook 用の会議アドインをアンインストールすることができます。これは、Live Meeting server とサービスベースの会議をスケジュールするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="d4ef1-168">ただし、Live Meeting サービス会議を継続してスケジュールする必要があるユーザーがいる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="d4ef1-169">この場合は、両方のアドインを共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="d4ef1-170">以前のクライアントを使用するフェデレーション組織との会議</span><span class="sxs-lookup"><span data-stu-id="d4ef1-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="d4ef1-171">Microsoft Office Communicator 2007 を使用しているフェデレーション組織のユーザーは、会議が開催者によってロックされている場合、組織内の Lync Server 2013 会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="d4ef1-172">会議の出席者が新しい https://会議の URL を使って会議に参加するときに、lync Web App を使うことができるように、Lync Server 2013 でこれらの会議のスケジュールを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ef1-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

