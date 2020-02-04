---
title: 'Lync Server 2013: Lync Server 2013 へのフェデレーションおよび外部アクセスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="07dfa-102">Lync Server 2013 へのフェデレーションおよび外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="07dfa-102">Managing federation and external access to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07dfa-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="07dfa-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="07dfa-104">エッジサーバーまたはエッジプールの展開は、外部ユーザーをサポートするための最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="07dfa-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="07dfa-105">エッジサーバーの展開の詳細については、展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07dfa-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="07dfa-106">Lync Server 2013 の内部展開をインストールして構成した後、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-106">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="07dfa-107">共同作業には、インスタントメッセージの送受信、プレゼンス状態の更新、会議 (「会議」とも呼ばれます) の参加が含まれます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-107">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="07dfa-108">外部ユーザーアクセスを有効にして構成し、サポートされている外部ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-108">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="07dfa-109">外部ユーザーには、展開のリモートユーザー、フェデレーションユーザー (パブリックインスタントメッセージング (IM) サービスプロバイダーのサポートされているユーザーを含む)、XMPP フェデレーション、および会議の匿名参加者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-109">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="07dfa-110">展開に Lync Server 2013 エッジサーバーまたはエッジプールのインストールが含まれている場合は、可能な通信の種類の範囲が、外部ユーザーアクセスのさまざまなオプションと、他の SIP フェデレーションドメインのメンバーとの通信に大きく拡張されています。SIP フェデレーションプロバイダーと XMPP フェデレーションされたユーザー。</span><span class="sxs-lookup"><span data-stu-id="07dfa-110">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="07dfa-111">エッジサーバーまたはエッジプールをセットアップした後、提供する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するためのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-111">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="07dfa-112">Lync server 2013 では、lync Server コントロールパネル、Lync Server 管理シェル、またはその両方を使用して、外部ユーザーのアクセスとポリシーを有効にし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-112">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="07dfa-113">これらの管理ツールの詳細については、「運用ドキュメントの[Lync server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)」、「運用ドキュメントの[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」、「運用ドキュメント」の「lync server [2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07dfa-113">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07dfa-114">外部ユーザーアクセスの構成とポリシーを設計する場合は、ポリシーの優先順位とポリシーの適用方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-114">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="07dfa-115">1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-115">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="07dfa-116">Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="07dfa-116">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="07dfa-117">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-117">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="07dfa-118">既定では、組織で外部ユーザーアクセスのサポートを有効にしている場合でも、リモートユーザーアクセス、フェデレーションされたユーザーアクセスなどの外部ユーザーアクセスをサポートするようにポリシーは構成されません。</span><span class="sxs-lookup"><span data-stu-id="07dfa-118">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="07dfa-119">外部ユーザーアクセスの使用を制御するには、1つ以上のポリシーを構成して、各ポリシーでサポートされている外部ユーザーアクセスの種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-119">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="07dfa-120">これには、次の外部アクセスポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-120">This includes the following external access policies:</span></span>

  - <span data-ttu-id="07dfa-121">**グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-121">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="07dfa-122">既定では、グローバルポリシーで外部ユーザーアクセスオプションは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="07dfa-122">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="07dfa-123">グローバルレベルで外部ユーザーのアクセスをサポートするには、1つ以上の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-123">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="07dfa-124">グローバルポリシーは組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="07dfa-124">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="07dfa-125">グローバルポリシーを削除しても、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="07dfa-125">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="07dfa-126">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="07dfa-126">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="07dfa-127">**サイトポリシー**   1 つ以上のサイトポリシーを作成し、構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-127">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="07dfa-128">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="07dfa-129">たとえば、グローバルポリシーでリモートユーザーアクセスを有効にする場合、特定のサイトのリモートユーザーアクセスを無効にするサイトポリシーを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-129">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="07dfa-130">既定では、サイトポリシーはそのサイトのすべてのユーザーに適用されますが、サイトポリシー設定を上書きするユーザーポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-130">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="07dfa-131">**ユーザーポリシー**   1 つまたは複数のユーザーポリシーを作成および構成して、リモートユーザーアクセスのサポートを特定のユーザーに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-131">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="07dfa-132">ユーザーポリシーの構成は、グローバルポリシーおよびサイトポリシーを上書きしますが、ユーザーポリシーが割り当てられている特定のユーザーに対してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-132">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="07dfa-133">たとえば、グローバルポリシーとサイトポリシーでリモートユーザーアクセスを有効にすると、リモートユーザーアクセスを無効にするユーザーポリシーを指定して、そのユーザーポリシーを特定のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-133">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="07dfa-134">ユーザーポリシーを作成する場合は、それを有効にする前に1人以上のユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-134">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="07dfa-135">作成または編集する必要のある構成設定とポリシーを決定するには、次の決定ポイントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07dfa-135">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="07dfa-136">**インスタントメッセージング、Web 会議、音声/ビデオを使用して、ドメインの内部および外部ユーザーが共同作業できるようにする必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-136">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="07dfa-137">「 [Lync server 2013 でリモートユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」および「 [lync server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」の説明に従って設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-137">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="07dfa-138">**組織内のユーザーによってホストされている会議への参加を匿名ユーザーに許可するかどうかを指定します。**</span><span class="sxs-lookup"><span data-stu-id="07dfa-138">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="07dfa-139">「Lync server [2013 で](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)会議ポリシーを割り当て、lync server 2013 の会議ポリシーを[作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」、「Lync server [2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」で説明するように設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-139">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="07dfa-140">**SIP フェデレーションドメイン連絡先との通信をユーザーに許可しますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-140">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="07dfa-141">「Lync server [2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「lync server [2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」、「lync server [2013 で組織の SIP フェデレーションドメインを管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)する」の説明に従って設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-141">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="07dfa-142">**SIP フェデレーションドメインとの通信を有効にしている場合は、XMPP フェデレーションパートナーの連絡先との通信を有効にしますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-142">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="07dfa-143">「[ポリシーを構成して、Lync server 2013 での XMPP フェデレーションユーザーアクセスを制御する](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)」および「 [lync server 2013 で xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」の説明に従って設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-143">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="07dfa-144">**SIP フェデレーションドメインとの通信を有効にしている場合、SIP フェデレーション自動検出を有効にしますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-144">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="07dfa-145">「 [Lync Server 2013 でフェデレーションパートナーの検出を有効または無効](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)にする」のトピックで詳しく説明するように設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-145">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="07dfa-146">**SIP フェデレーションドメインとの通信を有効にしている場合は、アーカイブを使用していて、通信がアーカイブされていることを通知するフェデレーションされた連絡先への免責事項の送信を有効にしますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-146">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="07dfa-147">「 [Lync Server 2013 のフェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」のトピックで詳しく説明するように設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-147">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="07dfa-148">**ユーザーに、Windows Live Messenger、AOL、Yahoo\!などのパブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信を許可しますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-148">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="07dfa-149">「 [Lync server 2013 でパブリックユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」の説明に従って設定を構成します。 lync server[2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にし、 [LYNC server 2013 でパブリック SIP フェデレーションプロバイダーを作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-149">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="07dfa-150">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="07dfa-150">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="07dfa-151">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-151">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="07dfa-152">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="07dfa-152">Messenger until the service shut down date.</span></span> <span data-ttu-id="07dfa-153">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="07dfa-153">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="07dfa-154">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="07dfa-154">has been announced.</span></span> <span data-ttu-id="07dfa-155">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07dfa-155">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="07dfa-156">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="07dfa-156">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="07dfa-157">Messenger.</span><span class="sxs-lookup"><span data-stu-id="07dfa-157">Messenger.</span></span> <span data-ttu-id="07dfa-158">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-158">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="07dfa-159">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="07dfa-159">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="07dfa-160">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="07dfa-160">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="07dfa-161">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-161">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="07dfa-162">**Microsoft Office 365、Microsoft Lync Online、Microsoft Lync Online 2010 を実行しているホスティングプロバイダーである SIP フェデレーションプロバイダーとの通信をユーザーに許可しますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-162">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft Office 365, Microsoft Lync Online and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="07dfa-163">トピック「 [lync server 2013 でパブリック SIP フェデレーションプロバイダーを作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)する」、「lync server [2013 でフェデレーションおよびパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」、「ホストされている[sip フェデレーションプロバイダーを作成または編集](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)する」の説明に従って設定を構成します。 lync server 2013</span><span class="sxs-lookup"><span data-stu-id="07dfa-163">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="07dfa-164">**展開は、分割 (ハイブリッド) ドメインで構成されます。一部のユーザーは、オンプレミスの展開でホームサーバーを使用していますが、他のユーザーはオンライン環境でホームサーバーを使用して構成されていますか?**</span><span class="sxs-lookup"><span data-stu-id="07dfa-164">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="07dfa-165">「Lync server [2013 でフェデレーションされたユーザーのアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「lync server [2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」、「ホストされた[SIP フェデレーションプロバイダーを作成または編集する」 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="07dfa-165">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="07dfa-166">要件を一覧表示するテーブルが必要な場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="07dfa-166">If you prefer a table that lists the requirements:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07dfa-167">フェデレーションおよび外部アクセス (分散) フェデレーションまたは外部アクセスの種類 (ダウン) のタブ</span><span class="sxs-lookup"><span data-stu-id="07dfa-167">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="07dfa-168">外部アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="07dfa-168">External Access Policy</span></span></th>
<th><span data-ttu-id="07dfa-169">Access Edge 構成</span><span class="sxs-lookup"><span data-stu-id="07dfa-169">Access Edge Config</span></span></th>
<th><span data-ttu-id="07dfa-170">SIP フェデレーションドメイン</span><span class="sxs-lookup"><span data-stu-id="07dfa-170">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="07dfa-171">SIP フェデレーション プロバイダー</span><span class="sxs-lookup"><span data-stu-id="07dfa-171">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="07dfa-172">XMPP フェデレーションパートナー</span><span class="sxs-lookup"><span data-stu-id="07dfa-172">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07dfa-173">リモートユーザー</span><span class="sxs-lookup"><span data-stu-id="07dfa-173">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="07dfa-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="07dfa-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07dfa-176">SIP フェデレーション連絡先</span><span class="sxs-lookup"><span data-stu-id="07dfa-176">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="07dfa-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="07dfa-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="07dfa-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="07dfa-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="07dfa-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07dfa-182">XMPP フェデレーション連絡先</span><span class="sxs-lookup"><span data-stu-id="07dfa-182">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="07dfa-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="07dfa-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="07dfa-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="07dfa-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07dfa-187">ドメイン/ハイブリッドユーザーの分割</span><span class="sxs-lookup"><span data-stu-id="07dfa-187">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="07dfa-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="07dfa-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07dfa-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07dfa-191">パブリック IM サービスの連絡先</span><span class="sxs-lookup"><span data-stu-id="07dfa-191">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="07dfa-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="07dfa-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07dfa-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07dfa-195">匿名ユーザーによる会議と会議へのアクセス</span><span class="sxs-lookup"><span data-stu-id="07dfa-195">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07dfa-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て</a></span><span class="sxs-lookup"><span data-stu-id="07dfa-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="07dfa-197">会議ポリシーの下で、次の構成設定を検討する必要があります。 <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Lync server 2013 の会議ポリシーを作成または変更</A>する、 <A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 の会議ポリシー設定リファレンス</A></span><span class="sxs-lookup"><span data-stu-id="07dfa-197">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07dfa-198">外部ユーザーアクセスを制御するために使用するポリシーなど、組織の外部ユーザーアクセスを有効にしていない場合でも、外部ユーザーアクセスの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-198">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization.</span></span> <span data-ttu-id="07dfa-199">ただし、構成したポリシーとその他の設定は、組織で外部ユーザーのアクセスが有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="07dfa-199">However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization.</span></span> <span data-ttu-id="07dfa-200">外部ユーザーのアクセスが無効になっている場合、または外部ユーザーのアクセスポリシーがサポートされていない場合、外部ユーザーは組織のユーザーと通信できません。</span><span class="sxs-lookup"><span data-stu-id="07dfa-200">External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="07dfa-201">エッジ展開では、外部ユーザーの種類 (会議 ID によって認証された匿名ユーザー、会議の作成および参加者の招待時に匿名の参加者に送信されるパスキー) を認証します。edge サポートの構成方法に基づくアクセス。</span><span class="sxs-lookup"><span data-stu-id="07dfa-201">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support.</span></span> <span data-ttu-id="07dfa-202">通信を制御するために、1つまたは複数のポリシーを構成し、展開の内外のユーザーとの通信方法を定義する設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-202">In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other.</span></span> <span data-ttu-id="07dfa-203">ポリシーと設定には、外部ユーザーアクセスの既定のグローバルポリシーに加えて、特定のサイトまたはユーザーに対して1つ以上の種類の外部ユーザーアクセスを有効にするために作成および構成できるサイトとユーザーのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="07dfa-203">The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07dfa-204">このセクション中</span><span class="sxs-lookup"><span data-stu-id="07dfa-204">In This Section</span></span>

  - [<span data-ttu-id="07dfa-205">Lync Server 2013 での組織の外部アクセス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="07dfa-205">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="07dfa-206">Lync Server 2013 での組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="07dfa-206">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="07dfa-207">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="07dfa-207">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="07dfa-208">Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="07dfa-208">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="07dfa-209">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</span><span class="sxs-lookup"><span data-stu-id="07dfa-209">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="07dfa-210">Lync Server 2013 での Lync Online ユーザーのフェデレーションサポートの構成</span><span class="sxs-lookup"><span data-stu-id="07dfa-210">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

