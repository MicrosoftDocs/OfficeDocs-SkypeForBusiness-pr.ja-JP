---
title: 'Lync Server 2013: アーカイブのしくみ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc6266cdf81f4462adf82c5878bcc47a6060fdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="e13f6-102">Lync Server 2013 でのアーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="e13f6-102">How Archiving works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e13f6-103">_**トピックの最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="e13f6-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="e13f6-104">Lync Server 2013 アーカイブは、コンプライアンス要件を満たすためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-104">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="e13f6-105">組織の要件を最も効果的に満たすように it を実装および管理するには、次のことを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-105">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="e13f6-106">アーカイブできる情報</span><span class="sxs-lookup"><span data-stu-id="e13f6-106">What information can be archived.</span></span>

  - <span data-ttu-id="e13f6-107">展開内でアーカイブを有効化および無効化する方法</span><span class="sxs-lookup"><span data-stu-id="e13f6-107">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="e13f6-108">アーカイブの実装方法を制御するために構成できるアーカイブ オプション</span><span class="sxs-lookup"><span data-stu-id="e13f6-108">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="e13f6-109">アーカイブできる情報</span><span class="sxs-lookup"><span data-stu-id="e13f6-109">What Information Can Be Archived?</span></span>

<span data-ttu-id="e13f6-110">次の種類のコンテンツをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-110">The following types of content can be archived:</span></span>

  - <span data-ttu-id="e13f6-111">ピアツーピアのインスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="e13f6-111">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="e13f6-112">マルチパーティのインスタント メッセージである会議 (ミーティング)</span><span class="sxs-lookup"><span data-stu-id="e13f6-112">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="e13f6-113">アップロードされたコンテンツ (配付資料など) およびイベント関連のコンテンツ (参加、退席、アップロード、共有、表示設定の変更など) を含む会議コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e13f6-113">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="e13f6-114">会議中に共有するホワイトボードおよび投票</span><span class="sxs-lookup"><span data-stu-id="e13f6-114">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="e13f6-115">次の種類のコンテンツはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-115">The following types of content are not archived:</span></span>

  - <span data-ttu-id="e13f6-116">ピアツーピア ファイル転送</span><span class="sxs-lookup"><span data-stu-id="e13f6-116">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="e13f6-117">ピアツーピアのインスタント メッセージおよび会議の音声ビデオ</span><span class="sxs-lookup"><span data-stu-id="e13f6-117">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="e13f6-118">ピアツーピアのインスタント メッセージおよび会議のデスクトップ/アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="e13f6-118">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="e13f6-119">また、Lync Server は常設チャットの会話をアーカイブしません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-119">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="e13f6-120">常設チャットの会話をアーカイブするには、コンプライアンスサービスを有効にして構成する必要があります。これは、Microsoft Lync Server 2013、常設チャットサーバーと共に展開できるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e13f6-120">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="e13f6-121">詳細については、「計画」のドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-121">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="e13f6-122">アーカイブの使用方法</span><span class="sxs-lookup"><span data-stu-id="e13f6-122">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="e13f6-p103">フロントエンド サーバーを展開すると、各サーバーにアーカイブ機能が自動的にインストールされます。ただし、アーカイブは構成するまで有効にはなりません。アーカイブを構成する方法は、アーカイブを展開する方法によって決まります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="e13f6-125">**Microsoft Exchange 統合を使用したアーカイブ。**</span><span class="sxs-lookup"><span data-stu-id="e13f6-125">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="e13f6-126">Exchange 2013 に所属していて、メールボックスがインプレース保持されているユーザーがいる場合は、Lync Server 2013 ストレージと Exchange 記憶域を統合するためのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-126">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="e13f6-127">[Microsoft Exchange 統合] オプションを選択する場合は、Exchange 2013 のポリシーと構成を使用して、これらのユーザーの Lync Server 2013 データのアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-127">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="e13f6-128">**Lync Server アーカイブデータベースを使用したアーカイブ。**</span><span class="sxs-lookup"><span data-stu-id="e13f6-128">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="e13f6-129">Exchange 2013 に所属していないユーザー、またはメールボックスがインプレース保持に配置されていないユーザー、または展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合は、SQL Server を使用して Lync Server アーカイブデータベースを展開できます。 これらのユーザーのアーカイブデータを格納する。</span><span class="sxs-lookup"><span data-stu-id="e13f6-129">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="e13f6-130">この場合、Lync Server 2013 のアーカイブポリシーと構成は、アーカイブが有効になっているかどうか、およびその実装方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-130">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="e13f6-131">Lync Server 2013 を使用するには、適切な SQL Server データベースをトポロジに追加し、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-131">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="e13f6-132">Microsoft Exchange 統合を使用する場合のアーカイブのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e13f6-132">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="e13f6-133">ユーザーが Exchange 2013 に所属しており、メールボックスがインプレース保持されている場合は、 **Microsoft Exchange 統合**オプション (このセクションで後述) を選択して、これらのユーザーの lync server 2013 をアーカイブし、次の項目を制御するために、Exchange のインプレース保持ポリシーと設定を指定して、これらのユーザーのアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-133">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="e13f6-134">IM、電話会議、またはこの両方をアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="e13f6-134">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="e13f6-135">Lync Server 展開に対して、重要モードを実装するかどうか。</span><span class="sxs-lookup"><span data-stu-id="e13f6-135">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="e13f6-136">Exchange 2013 を使用してアーカイブされたデータを保存するための Microsoft Exchange 統合オプションの選択。</span><span class="sxs-lookup"><span data-stu-id="e13f6-136">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="e13f6-137">これらの Lync Server 2013 アーカイブ構成オプションについては、このセクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-137">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="e13f6-138">アーカイブをサポートするように Exchange のインプレース保持ポリシーと設定を構成する方法については、Exchange 2013 製品のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-138">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="e13f6-139">Lync Server アーカイブ データベース ストレージを使用する場合のアーカイブのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e13f6-139">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="e13f6-140">Lync Server アーカイブデータベース (SQL Server データベースを使用) を使用して展開内の任意のユーザーのデータをアーカイブする場合は、Lync Server アーカイブポリシーを構成して、それらのユーザーに対してアーカイブを有効にするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-140">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="e13f6-141">各アーカイブ ポリシーでは、次のいずれかまたは両方のアーカイブを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-141">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="e13f6-142">内部通信</span><span class="sxs-lookup"><span data-stu-id="e13f6-142">Internal communications</span></span>

  - <span data-ttu-id="e13f6-143">外部通信</span><span class="sxs-lookup"><span data-stu-id="e13f6-143">External communications</span></span>

<span data-ttu-id="e13f6-144">既定では、すべての Lync Server アーカイブポリシーの内部通信または外部通信に対してアーカイブが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-144">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="e13f6-145">Lync server 2013 コントロールパネルを使用して、または Lync Server 2013 管理シェルでコマンドレットを使用して、通信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="e13f6-145">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="e13f6-146">Lync Server 2013 のアーカイブポリシーには、以下のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-146">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="e13f6-147">**グローバルアーカイブポリシー**。</span><span class="sxs-lookup"><span data-stu-id="e13f6-147">**Global Archiving policy**.</span></span> <span data-ttu-id="e13f6-148">これは既定のアーカイブポリシーで、展開全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-148">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="e13f6-149">これは、Lync Server 2013 を展開したときに作成されます。既定では、内部通信と外部通信の両方のアーカイブが無効になります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-149">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="e13f6-150">このポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-150">You cannot delete this policy.</span></span> <span data-ttu-id="e13f6-151">[削除] オプションを選択すると、グローバルポリシーが既定の設定にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-151">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="e13f6-p110">**サイト アーカイブ ポリシー:** 必要に応じて、特定のサイトを対象とするサイトレベルのアーカイブ ポリシーを作成し、構成することによって、1 つ以上のサイトでアーカイブを有効または無効にできます。サイトレベルのアーカイブ ポリシーを作成した場合、既定ではアーカイブは無効になっています。作成したサイトレベルのアーカイブ ポリシーは削除できます。サイトレベルのアーカイブ ポリシーは、グローバル ポリシーよりも優先されますが、そのポリシーで指定されたサイトだけが対象となります。たとえば、グローバル ポリシーで内部通信と外部通信のアーカイブを有効にし、外部通信のアーカイブを無効にするサイト ポリシーを作成した場合、そのサイトでは内部通信だけがアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="e13f6-p111">**ユーザー アーカイブ ポリシー:** 必要に応じて、指定したユーザーおよびユーザー グループを対象とするユーザーレベルのアーカイブ ポリシーを作成して構成し、適用することによって、1 人以上の特定のユーザーや 1 つ以上のユーザー グループに対してアーカイブを有効または無効にできます。ユーザーレベルのアーカイブ ポリシーを作成した場合、既定ではアーカイブは無効になっています。作成したユーザーレベルのアーカイブ ポリシーは削除できます。また、アーカイブ ポリシーを適用するユーザーおよびユーザー グループを変更することもできます。ユーザーレベルのアーカイブ ポリシーは、グローバル ポリシーおよびすべてのサイト ポリシーよりも優先されますが、そのポリシーが適用されたユーザーおよびユーザー グループだけが対象となります。たとえば、グローバル ポリシーで内部通信と外部通信のアーカイブを無効にし、内部通信と外部通信のアーカイブを有効にするサイトレベルのポリシーを作成して、外部通信のアーカイブを無効にするユーザーレベルのポリシーを作成した場合、すべてのサイト ユーザーに対して外部通信と内部通信の両方がアーカイブされます。ただし、ユーザーレベルのポリシーを適用したユーザーについては、内部通信だけがアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="e13f6-164">アーカイブを展開するときに初期アーカイブポリシーをセットアップする方法の詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのアーカイブポリシーの構成と割り当て](lync-server-2013-configuring-and-assigning-archiving-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-164">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="e13f6-165">展開後に通信を有効または無効にするためのアーカイブポリシーの使用の詳細については、「操作」のドキュメントの「 [Lync Server 2013 での内部および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-165">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e13f6-166">両方の Lync Server 2013 アーカイブデータベースを実装し、Microsoft Exchange 統合を有効にした場合、Exchange 2013 のポリシーは Lync Server アーカイブポリシーより優先されますが、exchange 2013 に所属しており、メールボックスがインプレース保持されていたユーザーに対してのみ有効です。.</span><span class="sxs-lookup"><span data-stu-id="e13f6-166">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e13f6-167">Lync アーカイブは、Microsoft Exchange のインプレース保持ポリシーのみに依存します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-167">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="e13f6-168">アーカイブの構成で使用できるオプション</span><span class="sxs-lookup"><span data-stu-id="e13f6-168">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="e13f6-169">ポリシーを使用してアーカイブを有効化および無効化する以外に、展開全体、特定のサイト、または特定のプールに対して構成できるその他のアーカイブ オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-169">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="e13f6-170">ほとんどのアーカイブオプションは、Lync Server 2013 コントロールパネルで利用できる1つまたは複数のアーカイブ構成を使用して制御できますが、Lync Server 2013 管理シェルを使用した構成でのみ使用可能な別のオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-170">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="e13f6-171">Lync Server 2013 コントロール パネルで使用可能なアーカイブ構成オプション</span><span class="sxs-lookup"><span data-stu-id="e13f6-171">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="e13f6-172">各アーカイブ構成には、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-172">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="e13f6-p115">グローバルレベルの構成は、アーカイブを展開したときに自動的に作成されます。構成はできますが、削除はできません。グローバル構成の削除オプションを選択すると、設定が既定値にリセットされます。複数のサイト構成およびプール構成を作成し、グローバル構成と共にアーカイブ設定を制御できます。グローバル構成とそれぞれのサイト構成およびプール構成には、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="e13f6-177">アーカイブの無効化、インスタント メッセージング (IM) のみアーカイブを有効化、または IM と会議の両方のアーカイブの有効化を指定する。</span><span class="sxs-lookup"><span data-stu-id="e13f6-177">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="e13f6-178">Lync Server に障害が発生した場合に IM および会議セッションをブロックするように、重要モードを構成します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-178">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="e13f6-179">障害には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-179">Failures include the following:</span></span>
    
      - <span data-ttu-id="e13f6-180">**IM**。</span><span class="sxs-lookup"><span data-stu-id="e13f6-180">**IM**.</span></span> <span data-ttu-id="e13f6-181">Lync Server ストレージサービスに関する問題。</span><span class="sxs-lookup"><span data-stu-id="e13f6-181">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="e13f6-182">この場合、アーカイブが有効になっているユーザーでは IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-182">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="e13f6-p118">**電話会議:** ファイル共有を使用できない障害や、ストレージ サービスの問題が発生する場合があります。この場合、障害発生時にプール内でホストされているアクティブな会議がすべて制限モードに切り替えられ、新しい会議をアクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="e13f6-186">障害から回復した後、IM および会議は自動的に回復します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-186">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="e13f6-187">Lync Server 2013 アーカイブデータを格納するために個別の SQL Server データベースを設定する代わりに、Microsoft Exchange Server 2013 統合を使用して、アーカイブされたデータの格納に Exchange 2013 を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-187">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="e13f6-p119">アーカイブされたデータの削除オプションを構成する。アーカイブされたデータの削除のタイミングを次のどちらかから指定できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="e13f6-190">指定した日数経過後</span><span class="sxs-lookup"><span data-stu-id="e13f6-190">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="e13f6-191">アーカイブデータがエクスポートされた後 (Microsoft Exchange 統合を有効にした場合は、Exchange にアップロードされたデータが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="e13f6-191">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e13f6-192">Microsoft Exchange 統合を有効にした場合、Exchange 2013 に所属するユーザーとメールボックスがインプレース保持になっているユーザーの削除は、Exchange によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-192">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="e13f6-193">唯一の資格は、Lync Server ファイル共有に格納されている会議ファイル用です。</span><span class="sxs-lookup"><span data-stu-id="e13f6-193">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="e13f6-194">これらのファイルは、アーカイブ データがエクスポートされた後でデータを削除するオプションを選択した場合はファイルがエクスポートされた後 (Exchange にアップロードされた後)、保持する最大日数を指定した場合は指定した最大日数経過後にのみファイル共有から削除されます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-194">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="e13f6-195">既定で、すべてのアーカイブ オプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e13f6-195">By default, no archiving options are enabled.</span></span> <span data-ttu-id="e13f6-196">Lync Server 2013 コントロールパネルを使用してアーカイブ構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-196">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="e13f6-197">次のアーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-197">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="e13f6-198">**グローバル アーカイブ構成**。</span><span class="sxs-lookup"><span data-stu-id="e13f6-198">**Global Archiving configuration**.</span></span> <span data-ttu-id="e13f6-199">既定のアーカイブ構成であり、展開全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-199">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="e13f6-200">これは、Lync Server 2013 を展開したときに作成されます。既定では、アーカイブ機能は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-200">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="e13f6-201">グローバル構成は、変更はできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-201">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="e13f6-202">構成の削除オプションを選択すると、グローバル構成が既定の設定にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-202">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="e13f6-p123">**サイト アーカイブ構成**。個別のサイトに対してサイトレベルのアーカイブ構成を作成および構成することによって、1 つ以上の特定のサイトのアーカイブを構成できます。サイトレベルのアーカイブ構成は、作成した場合にのみ存在します。任意のサイトレベルのアーカイブ構成を変更または削除できます。サイトレベルのアーカイブ構成は、そのサイトレベルの構成で指定されたサイトにおいてのみグローバル構成よりも優先されます。たとえば、グローバル構成で IM のアーカイブのみを有効にし、IM と会議の両方のアーカイブを有効にするサイト構成を作成した場合、会議はそのサイトでのみアーカイブされ、組織内の他のサイトではアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="e13f6-p124">**プール アーカイブ構成**。個別のプールに対してプールレベルの構成を作成および構成することによって、1 つ以上の特定のプールに対してアーカイブ設定を指定できます。プールレベルのアーカイブ構成は、作成した場合にのみ存在します。任意のプールレベルのアーカイブ構成を変更および削除できます。プールレベルのアーカイブ構成は、グローバル構成、および作成した任意のサイト アーカイブ構成よりも優先されます。たとえば、グローバル構成で IM のアーカイブのみを有効にし、サイトに対して IM と会議の両方のアーカイブを有効にするサイトレベルの構成を作成して、IM のアーカイブのみを有効にするプールレベルのアーカイブ構成を作成した場合、プールレベルの構成で指定されたプールに所属するユーザーを除いて、サイトのすべてのユーザーでは IM と会議の両方の通信がアーカイブされます。組織内のすべての他のユーザーでは、IM のアーカイブのみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="e13f6-216">アーカイブを展開するときに初期アーカイブ構成をセットアップする方法の詳細については、「展開」のドキュメントの「 [Lync Server 2013 のアーカイブオプションの構成](lync-server-2013-configuring-archiving-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-216">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="e13f6-217">展開後に通信を有効または無効にするためのアーカイブポリシーの使用の詳細については、「操作」のドキュメントの「 [Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-217">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="e13f6-218">Windows PowerShell でのみ使用可能なアーカイブ オプション</span><span class="sxs-lookup"><span data-stu-id="e13f6-218">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="e13f6-219">Lync Server 2013 管理シェルを使用すると、コマンドレットを使用して Lync Server 2013 コントロールパネルでは使用できないオプションを実装できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-219">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="e13f6-220">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-220">These options include the following:</span></span>

  - <span data-ttu-id="e13f6-221">**重複するメッセージをアーカイブ**します。</span><span class="sxs-lookup"><span data-stu-id="e13f6-221">**Archive duplicate messages**.</span></span> <span data-ttu-id="e13f6-222">詳細については、「操作」のドキュメントの「 [set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 」と「 [set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-222">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="e13f6-223">**アーカイブ**されたデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e13f6-223">**Export archived data**.</span></span> <span data-ttu-id="e13f6-224">詳細については、「 [export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-224">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="e13f6-225">アーカイブされたデータへのアクセス方法</span><span class="sxs-lookup"><span data-stu-id="e13f6-225">How Do I Access Archived Data?</span></span>

<span data-ttu-id="e13f6-226">アーカイブされたデータへのアクセス方法は、データの保管場所に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-226">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="e13f6-227">**Microsoft Exchange ストレージ**</span><span class="sxs-lookup"><span data-stu-id="e13f6-227">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="e13f6-228">Exchange 統合オプションを選択した場合、Lync Server は exchange 2013 に所属しているすべてのユーザーに対して Exchange 2013 ストア内のアーカイブコンテンツをデポジットし、メールボックスがインプレース保持されているすべてのユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e13f6-228">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e13f6-229">アーカイブされたデータはユーザーのメールボックスの回復可能なアイテムフォルダーに格納されます。これは通常、ユーザーには表示されず、Exchange の**検出管理**の役割を持つユーザーのみが検索できます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-229">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="e13f6-230">Exchange では、展開されている場合は SharePoint と共にフェデレーション検索と検出が有効になります。</span><span class="sxs-lookup"><span data-stu-id="e13f6-230">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="e13f6-231">Exchange に格納されているデータの記憶域、保持、および検出の詳細については、「Exchange 2013 および SharePoint のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-231">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="e13f6-232">**Lync Server ストレージ**。</span><span class="sxs-lookup"><span data-stu-id="e13f6-232">**Lync Server storage**.</span></span> <span data-ttu-id="e13f6-233">Lync server データのストレージ用に Lync Server 2013 アーカイブデータベースを設定すると、Lync server は、Exchange 2013 に所属していないユーザーの Lync Server アーカイブデータベース (SQL Server データベース) にあるアーカイブコンテンツをデポジットし、メールボックスが配置されていないユーザーを対象としています。インプレースホールド。</span><span class="sxs-lookup"><span data-stu-id="e13f6-233">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e13f6-234">このデータは検索できませんが、他のツールを使用して検索可能な形式にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e13f6-234">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="e13f6-235">アーカイブデータベースに格納されているデータのエクスポートの詳細については、「操作」のドキュメントの「 [Lync Server 2013 からアーカイブデータをエクスポート](lync-server-2013-exporting-archived-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-235">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="e13f6-236">Lync Server 2013 と Exchange 2013 の連携の詳細については、「サポート」のドキュメントの「 [Lync server 2013 での Exchange Server と SharePoint の統合のサポート](lync-server-2013-exchange-and-sharepoint-integration-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13f6-236">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

