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
ms.openlocfilehash: 2adaff02f6533b463199b5d295f65cc519a784e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="402d7-102">Lync Server 2013 へのフェデレーションおよび外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="402d7-102">Managing federation and external access to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="402d7-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="402d7-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="402d7-104">外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="402d7-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="402d7-105">エッジサーバーの展開の詳細については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402d7-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="402d7-106">Lync Server 2013 の内部展開をインストールして構成すると、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="402d7-106">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="402d7-107">共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。</span><span class="sxs-lookup"><span data-stu-id="402d7-107">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="402d7-108">サポートされている外部ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御するために、外部ユーザーアクセスを有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-108">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="402d7-109">外部ユーザーには、展開のリモート ユーザー、フェデレーション ユーザー (パブリック インスタント メッセージング (IM) サービス プロバイダーのサポートされるユーザーを含む)、XMPP フェデレーション、および電話会議への匿名参加者などのユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="402d7-109">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="402d7-110">展開に Lync Server 2013 エッジサーバーまたはエッジプールのインストールが含まれていた場合、考えられる通信の種類の範囲は、外部ユーザーアクセス、他の SIP フェデレーションドメインのメンバーとの通信のためのさまざまなオプションを使用して大幅に拡張されます。SIP フェデレーションプロバイダー、および XMPP フェデレーションユーザー。</span><span class="sxs-lookup"><span data-stu-id="402d7-110">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="402d7-111">エッジサーバーまたはエッジプールを設定したら、指定する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-111">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="402d7-112">Lync Server 2013 では、タスクの要件に基づいて Lync server コントロールパネル、Lync Server 管理シェル、またはその両方を使用して、外部ユーザーアクセスとポリシーを有効にし、構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-112">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="402d7-113">これらの管理ツールの詳細については、「操作」のドキュメントの「 [lync server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)」、「操作」のドキュメントの「lync Server [2013 management Shell](lync-server-2013-lync-server-management-shell.md) 」、および「操作」のドキュメントの「lync server [2013 管理ツールのインストール](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402d7-113">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="402d7-114">外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="402d7-114">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="402d7-115">あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="402d7-115">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="402d7-116">Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。</span><span class="sxs-lookup"><span data-stu-id="402d7-116">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="402d7-117">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="402d7-117">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="402d7-p105">組織の外部ユーザー アクセス サポートが既に有効になっている場合でも、既定では、リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど、外部ユーザー アクセスをサポートするポリシーは構成されません。 外部ユーザー アクセスを制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。 これには、次の外部アクセス ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="402d7-p105">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. This includes the following external access policies:</span></span>

  - <span data-ttu-id="402d7-121">**グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="402d7-121">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="402d7-122">既定では、グローバルポリシーでは、外部ユーザーアクセスオプションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="402d7-122">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="402d7-123">グローバルレベルで外部ユーザーアクセスをサポートするには、1つまたは複数の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-123">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="402d7-124">グローバルポリシーは、組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="402d7-124">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="402d7-125">グローバルポリシーを削除した場合は、削除しないようにします。</span><span class="sxs-lookup"><span data-stu-id="402d7-125">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="402d7-126">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="402d7-126">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="402d7-127">**サイトポリシー**   1 つ以上のサイトポリシーを作成および構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="402d7-127">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="402d7-128">サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。</span><span class="sxs-lookup"><span data-stu-id="402d7-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="402d7-129">たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。</span><span class="sxs-lookup"><span data-stu-id="402d7-129">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="402d7-130">既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="402d7-130">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="402d7-131">**ユーザーポリシー**   1 つ以上のユーザーポリシーを作成および構成して、特定のユーザーへのリモートユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="402d7-131">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="402d7-132">ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="402d7-132">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="402d7-133">たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。</span><span class="sxs-lookup"><span data-stu-id="402d7-133">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="402d7-134">ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。</span><span class="sxs-lookup"><span data-stu-id="402d7-134">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="402d7-135">どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="402d7-135">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="402d7-136">**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-136">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="402d7-137">トピック「 [lync server 2013 でリモートユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」、および「 [lync server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-137">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="402d7-138">**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-138">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="402d7-139">トピック「lync server [2013 での匿名ユーザーのサポートのための会議](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)ポリシーの割り当て」、「lync server [2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)」、および「 [lync server 2013 の会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-139">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="402d7-140">**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-140">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="402d7-141">「Lync server [2013 でフェデレーションユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM Connectivity in lync server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「 [lync server 2013 での組織の SIP フェデレーションドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-141">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="402d7-142">**SIP フェデレーション ドメインとの通信を有効化した場合、XMPP フェデレーション パートナーの連絡先との通信を有効化するか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-142">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="402d7-143">トピック「 [configure policies to CONTROL The Lync server 2013 での xmpp フェデレーションユーザーアクセスを制御する](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)」および「 [lync server 2013 で xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-143">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="402d7-144">**SIP フェデレーションドメインとの通信を有効にしている場合は、SIP フェデレーションの自動検出を有効にしますか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-144">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="402d7-145">トピック「 [Lync Server 2013 でのフェデレーションパートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)」に記載されているとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-145">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="402d7-146">**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-146">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="402d7-147">トピック「 [Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」で説明されているとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-147">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="402d7-148">**ユーザーに、Windows Live Messenger、AOL、Yahoo\!などのパブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信を許可するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-148">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="402d7-149">トピック「lync server [2013 でパブリックユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」の説明に従って設定を構成します。 lync server[2013 の [フェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)]、および[lync SERVER 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="402d7-149">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="402d7-150">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="402d7-150">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="402d7-151">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="402d7-151">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="402d7-152">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="402d7-152">Messenger until the service shut down date.</span></span> <span data-ttu-id="402d7-153">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="402d7-153">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="402d7-154">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="402d7-154">has been announced.</span></span> <span data-ttu-id="402d7-155">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402d7-155">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="402d7-156">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="402d7-156">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="402d7-157">Messenger.</span><span class="sxs-lookup"><span data-stu-id="402d7-157">Messenger.</span></span> <span data-ttu-id="402d7-158">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="402d7-158">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="402d7-159">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="402d7-159">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="402d7-160">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="402d7-160">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="402d7-161">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="402d7-161">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="402d7-162">**ユーザーに対して、Microsoft Office 365、Microsoft Lync Online、Microsoft Lync Online 2010 を実行しているホストされているプロバイダーである SIP フェデレーションプロバイダーとの通信を許可しますか?**</span><span class="sxs-lookup"><span data-stu-id="402d7-162">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft Office 365, Microsoft Lync Online and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="402d7-163">トピック「lync server [2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)」、「 [Enable or disable FEDERATION and public IM Connectivity in lync server 2013」](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 、および「 [create or Edit Hosted SIP フェデレーションプロバイダ lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-163">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="402d7-164">**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**</span><span class="sxs-lookup"><span data-stu-id="402d7-164">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="402d7-165">トピック「lync server [2013 でフェデレーションユーザーアクセスを制御するためのポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM connectivity in lync server 2013」](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 、および「 [Create or Edit Hosted SIP フェデレーションプロバイダ lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 」の説明のとおりに設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="402d7-165">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="402d7-166">次に、要件を一覧表示した表を示します。</span><span class="sxs-lookup"><span data-stu-id="402d7-166">If you prefer a table that lists the requirements:</span></span>


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
<th><span data-ttu-id="402d7-167">フェデレーションのタブと外部アクセス (経由) フェデレーションまたは外部アクセスの種類 (下)</span><span class="sxs-lookup"><span data-stu-id="402d7-167">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="402d7-168">外部アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="402d7-168">External Access Policy</span></span></th>
<th><span data-ttu-id="402d7-169">アクセス エッジ構成</span><span class="sxs-lookup"><span data-stu-id="402d7-169">Access Edge Config</span></span></th>
<th><span data-ttu-id="402d7-170">SIP フェデレーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="402d7-170">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="402d7-171">SIP フェデレーション プロバイダー</span><span class="sxs-lookup"><span data-stu-id="402d7-171">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="402d7-172">XMPP フェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="402d7-172">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="402d7-173">リモート ユーザー</span><span class="sxs-lookup"><span data-stu-id="402d7-173">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="402d7-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="402d7-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="402d7-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="402d7-176">SIP フェデレーションからの連絡先</span><span class="sxs-lookup"><span data-stu-id="402d7-176">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="402d7-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="402d7-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="402d7-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="402d7-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="402d7-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="402d7-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</a></span><span class="sxs-lookup"><span data-stu-id="402d7-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="402d7-182">XMPP フェデレーションからの連絡先</span><span class="sxs-lookup"><span data-stu-id="402d7-182">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="402d7-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="402d7-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="402d7-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="402d7-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="402d7-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="402d7-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013 での XMPP フェデレーションパートナーの管理</a></span><span class="sxs-lookup"><span data-stu-id="402d7-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="402d7-187">分割ドメイン/ハイブリッド ユーザー</span><span class="sxs-lookup"><span data-stu-id="402d7-187">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="402d7-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="402d7-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="402d7-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="402d7-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する</a></span><span class="sxs-lookup"><span data-stu-id="402d7-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="402d7-191">パブリック IM サービスの連絡先</span><span class="sxs-lookup"><span data-stu-id="402d7-191">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="402d7-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="402d7-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="402d7-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="402d7-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="402d7-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="402d7-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="402d7-195">会議や電話会議への匿名ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="402d7-195">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="402d7-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て</a></span><span class="sxs-lookup"><span data-stu-id="402d7-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="402d7-197">また、「会議ポリシー: lync <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">server 2013 での会議ポリシーの作成または変更」</A>および「 <A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 の会議ポリシー設定リファレンス</A>」の下にある次の構成設定を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="402d7-197">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="402d7-p112">ユーザーは、組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセスの制御に使用する任意のポリシーを含む、外部ユーザー アクセス設定を構成できます。ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。外部ユーザー アクセスが無効になっている場合やサポートする外部ユーザー アクセス ポリシーが構成されていない場合、外部ユーザーは組織のユーザーと通信できません。</span><span class="sxs-lookup"><span data-stu-id="402d7-p112">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization. However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization. External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="402d7-p113">エッジ展開は、エッジ サポートの構成方法に応じて、外部ユーザーの種類を認証し (匿名ユーザーは例外。匿名ユーザーは、会議を作成して参加者を招待した時に匿名の参加者に送信される会議 ID とパスキーによって認証)、アクセスを制御します。通信を制御するために、展開の内側と外側のユーザーが互いに通信する方法を定義する 1 つ以上のポリシーおよび設定を構成できます。ポリシーと設定には、特定のサイトまたはユーザーについて 1 つ以上の種類の外部ユーザー アクセスを有効にするために作成および構成できるサイト ポリシーおよびユーザー ポリシーに加えて、外部ユーザー アクセスの既定のグローバル ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="402d7-p113">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support. In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other. The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="402d7-204">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="402d7-204">In This Section</span></span>

  - [<span data-ttu-id="402d7-205">Lync Server 2013 での外部アクセスポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="402d7-205">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="402d7-206">Lync Server 2013 での組織のアクセスエッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="402d7-206">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="402d7-207">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</span><span class="sxs-lookup"><span data-stu-id="402d7-207">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="402d7-208">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="402d7-208">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="402d7-209">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="402d7-209">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="402d7-210">Lync Server 2013 で Lync Online 顧客のフェデレーションサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="402d7-210">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

