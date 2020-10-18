---
title: 'Lync Server 2013: Lync Server 2013 へのフェデレーションおよび外部アクセスの管理'
description: 'Lync Server 2013: Lync Server 2013 へのフェデレーションと外部アクセスを管理します。'
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
ms.openlocfilehash: d1d389c7490fd1884631ed2fc184d590eb42141b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574923"
---
# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="8e30b-103">Lync Server 2013 へのフェデレーションおよび外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="8e30b-103">Managing federation and external access to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e30b-104">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8e30b-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8e30b-105">外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-105">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="8e30b-106">エッジサーバーの展開の詳細については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e30b-106">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8e30b-107">Lync Server 2013 の内部展開をインストールして構成すると、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-107">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="8e30b-108">共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-108">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="8e30b-109">サポートされている外部ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御するために、外部ユーザーアクセスを有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-109">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="8e30b-110">外部ユーザーには、展開のリモート ユーザー、フェデレーション ユーザー (パブリック インスタント メッセージング (IM) サービス プロバイダーのサポートされるユーザーを含む)、XMPP フェデレーション、および電話会議への匿名参加者などのユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-110">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="8e30b-111">展開に Lync Server 2013 エッジサーバーまたはエッジプールのインストールが含まれていた場合、考えられる通信の種類の範囲は、外部ユーザーアクセスのさまざまなオプション、他の SIP フェデレーションドメインのメンバーとの通信、SIP フェデレーションプロバイダー、および XMPP フェデレーションユーザーによって大幅に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-111">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="8e30b-112">エッジサーバーまたはエッジプールを設定したら、指定する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-112">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="8e30b-113">Lync Server 2013 では、タスクの要件に基づいて Lync server コントロールパネル、Lync Server 管理シェル、またはその両方を使用して、外部ユーザーアクセスとポリシーを有効にし、構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-113">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="8e30b-114">これらの管理ツールの詳細については、「操作」のドキュメントの「 [lync server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md) 」、「操作」のドキュメントの「lync Server [2013 management Shell](lync-server-2013-lync-server-management-shell.md) 」、および「操作」のドキュメントの「lync server [2013 管理ツールのインストール](lync-server-2013-install-lync-server-administrative-tools.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e30b-114">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e30b-115">外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-115">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="8e30b-116">あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-116">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="8e30b-117">Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-117">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="8e30b-118">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-118">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="8e30b-p105">組織の外部ユーザー アクセス サポートが既に有効になっている場合でも、既定では、リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど、外部ユーザー アクセスをサポートするポリシーは構成されません。 外部ユーザー アクセスを制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。 これには、次の外部アクセス ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-p105">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. This includes the following external access policies:</span></span>

  - <span data-ttu-id="8e30b-122">**グローバル ポリシー**   グローバル ポリシーは、エッジ サーバーを展開する際に作成されます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-122">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="8e30b-123">既定では、グローバル ポリシーではどの外部ユーザー アクセス オプションも有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="8e30b-123">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="8e30b-124">グローバル レベルで外部ユーザー アクセスをサポートするには、1 つ以上の外部ユーザー アクセス オプションをサポートするようにグローバル ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-124">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="8e30b-125">グローバル ポリシーは組織内のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="8e30b-125">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="8e30b-126">グローバル ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e30b-126">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="8e30b-127">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="8e30b-127">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="8e30b-128">**サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに限定するために、1 つ以上のサイト ポリシーを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-128">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="8e30b-129">サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。</span><span class="sxs-lookup"><span data-stu-id="8e30b-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="8e30b-130">たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。</span><span class="sxs-lookup"><span data-stu-id="8e30b-130">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="8e30b-131">既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-131">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="8e30b-132">**ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに限定するために、1 つ以上のユーザー ポリシーを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-132">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="8e30b-133">ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="8e30b-133">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="8e30b-134">たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。</span><span class="sxs-lookup"><span data-stu-id="8e30b-134">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="8e30b-135">ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。</span><span class="sxs-lookup"><span data-stu-id="8e30b-135">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="8e30b-136">どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e30b-136">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="8e30b-137">**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-137">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="8e30b-138">トピック「 [lync server 2013 でリモートユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」、および「 [lync server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-138">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="8e30b-139">**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-139">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="8e30b-140">トピック「lync server [2013 での匿名ユーザーのサポートのための会議](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)ポリシーの割り当て」、「lync server [2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)」、および「 [lync server 2013 の会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-140">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="8e30b-141">**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-141">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="8e30b-142">「Lync server [2013 でフェデレーションユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM Connectivity in lync server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「 [lync server 2013 での組織の SIP フェデレーションドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-142">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="8e30b-143">**SIP フェデレーション ドメインとの通信を有効化した場合、XMPP フェデレーション パートナーの連絡先との通信を有効化するか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-143">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="8e30b-144">トピック「 [configure policies to CONTROL The Lync server 2013 での xmpp フェデレーションユーザーアクセスを制御する](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) 」および「 [lync server 2013 で xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-144">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="8e30b-145">**SIP フェデレーションドメインとの通信を有効にしている場合は、SIP フェデレーションの自動検出を有効にしますか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-145">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="8e30b-146">トピック「 [Lync Server 2013 でのフェデレーションパートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)」に記載されているとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-146">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="8e30b-147">**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-147">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="8e30b-148">トピック「 [Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」で説明されているとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-148">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="8e30b-149">**ユーザーに、Windows Live Messenger、AOL、Yahoo などのパブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信を許可する \! かどうか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-149">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="8e30b-150">トピック「lync server [2013 でパブリックユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」の説明に従って設定を構成します。 lync server[2013 の [フェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)]、および[lync SERVER 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="8e30b-150">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="8e30b-151">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8e30b-151">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="8e30b-152">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-152">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8e30b-153">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="8e30b-153">Messenger until the service shut down date.</span></span> <span data-ttu-id="8e30b-154">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="8e30b-154">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8e30b-155">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="8e30b-155">has been announced.</span></span> <span data-ttu-id="8e30b-156">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e30b-156">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="8e30b-157">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="8e30b-157">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8e30b-158">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8e30b-158">Messenger.</span></span> <span data-ttu-id="8e30b-159">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="8e30b-159">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="8e30b-160">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="8e30b-160">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8e30b-161">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8e30b-161">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8e30b-162">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-162">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="8e30b-163">**ユーザーが、Microsoft 365、Microsoft Lync Online、Microsoft Lync Online 2010 を実行しているホストされているプロバイダーである SIP フェデレーションプロバイダーとの通信を許可するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-163">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft 365, Microsoft Lync Online, and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="8e30b-164">トピック「lync server [2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)」、「 [Enable or disable FEDERATION and public IM Connectivity in lync server 2013」](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 、および「 [create or Edit Hosted SIP フェデレーションプロバイダ lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-164">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="8e30b-165">**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**</span><span class="sxs-lookup"><span data-stu-id="8e30b-165">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="8e30b-166">トピック「lync server [2013 でフェデレーションユーザーアクセスを制御するためのポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM connectivity in lync server 2013」](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 、および「 [Create or Edit Hosted SIP フェデレーションプロバイダ lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-166">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="8e30b-167">次に、要件を一覧表示した表を示します。</span><span class="sxs-lookup"><span data-stu-id="8e30b-167">If you prefer a table that lists the requirements:</span></span>


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
<th><span data-ttu-id="8e30b-168">フェデレーションのタブと外部アクセス (経由) フェデレーションまたは外部アクセスの種類 (下)</span><span class="sxs-lookup"><span data-stu-id="8e30b-168">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="8e30b-169">外部アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="8e30b-169">External Access Policy</span></span></th>
<th><span data-ttu-id="8e30b-170">アクセス エッジ構成</span><span class="sxs-lookup"><span data-stu-id="8e30b-170">Access Edge Config</span></span></th>
<th><span data-ttu-id="8e30b-171">SIP フェデレーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="8e30b-171">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="8e30b-172">SIP フェデレーション プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8e30b-172">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="8e30b-173">XMPP フェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="8e30b-173">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e30b-174">リモート ユーザー</span><span class="sxs-lookup"><span data-stu-id="8e30b-174">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="8e30b-175"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-175"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8e30b-176"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-176"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e30b-177">SIP フェデレーションからの連絡先</span><span class="sxs-lookup"><span data-stu-id="8e30b-177">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="8e30b-178"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-178"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8e30b-179"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-179"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8e30b-180"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-180"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8e30b-181"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-181"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8e30b-182"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-182"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e30b-183">XMPP フェデレーションからの連絡先</span><span class="sxs-lookup"><span data-stu-id="8e30b-183">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="8e30b-184"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-184"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8e30b-185"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-185"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8e30b-186"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-186"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8e30b-187"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013 での XMPP フェデレーションパートナーの管理</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-187"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e30b-188">分割ドメイン/ハイブリッド ユーザー</span><span class="sxs-lookup"><span data-stu-id="8e30b-188">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="8e30b-189"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-189"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8e30b-190"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-190"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e30b-191"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-191"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e30b-192">パブリック IM サービスの連絡先</span><span class="sxs-lookup"><span data-stu-id="8e30b-192">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="8e30b-193"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-193"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8e30b-194"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-194"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e30b-195"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-195"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e30b-196">会議や電話会議への匿名ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="8e30b-196">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e30b-197"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て</a></span><span class="sxs-lookup"><span data-stu-id="8e30b-197"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8e30b-198">また、「会議ポリシー: lync <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">server 2013 での会議ポリシーの作成または変更」</A>および「 <A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 の会議ポリシー設定リファレンス</A>」の下にある次の構成設定を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e30b-198">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e30b-p112">ユーザーは、組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセスの制御に使用する任意のポリシーを含む、外部ユーザー アクセス設定を構成できます。ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。外部ユーザー アクセスが無効になっている場合やサポートする外部ユーザー アクセス ポリシーが構成されていない場合、外部ユーザーは組織のユーザーと通信できません。</span><span class="sxs-lookup"><span data-stu-id="8e30b-p112">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization. However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization. External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="8e30b-p113">エッジ展開は、エッジ サポートの構成方法に応じて、外部ユーザーの種類を認証し (匿名ユーザーは例外。匿名ユーザーは、会議を作成して参加者を招待した時に匿名の参加者に送信される会議 ID とパスキーによって認証)、アクセスを制御します。通信を制御するために、展開の内側と外側のユーザーが互いに通信する方法を定義する 1 つ以上のポリシーおよび設定を構成できます。ポリシーと設定には、特定のサイトまたはユーザーについて 1 つ以上の種類の外部ユーザー アクセスを有効にするために作成および構成できるサイト ポリシーおよびユーザー ポリシーに加えて、外部ユーザー アクセスの既定のグローバル ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e30b-p113">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support. In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other. The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e30b-205">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8e30b-205">In This Section</span></span>

  - [<span data-ttu-id="8e30b-206">Lync Server 2013 での外部アクセスポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="8e30b-206">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="8e30b-207">Lync Server 2013 での組織のアクセスエッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="8e30b-207">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="8e30b-208">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</span><span class="sxs-lookup"><span data-stu-id="8e30b-208">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="8e30b-209">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="8e30b-209">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="8e30b-210">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="8e30b-210">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="8e30b-211">Lync Server 2013 で Lync Online 顧客のフェデレーションサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="8e30b-211">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

