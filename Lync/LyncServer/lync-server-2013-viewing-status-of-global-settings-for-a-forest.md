---
title: 'Lync Server 2013: フォレストのグローバル設定の状態を表示する'
description: 'Lync Server 2013: フォレストのグローバル設定の状態を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567593"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="8820e-103">Lync Server 2013 のフォレストのグローバル設定の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="8820e-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8820e-104">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="8820e-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="8820e-105">管理者は、Lync Server 2013 展開のグローバル設定を毎月確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="8820e-106">目的は、一連の既知の構成に対して実装済みの設定を確認することです。基準構成は、設定が有効であることを保証し、ベースラインのドキュメントを更新する必要があるかどうかを判断するためのものです。</span><span class="sxs-lookup"><span data-stu-id="8820e-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="8820e-107">グローバル設定の変更は、新しい設定を文書化することを含める必要がある変更管理プロセスによって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="8820e-108">次のセクションでは、確認が必要なグローバル設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="8820e-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="8820e-109">全般設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-109">Check general settings</span></span>

<span data-ttu-id="8820e-110">Lync Server 2013 でサポートされているセッション開始プロトコル (SIP) ドメインなど、全般設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="8820e-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="8820e-111">SIP ドメイン情報は、Windows PowerShell と **new-cssipdomain** コマンドレットを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="8820e-112">この情報を取得するには、 `Get-CsSipDomain` Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8820e-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="8820e-113">Get-CsSipDomain は、認証されたすべての SIP ドメインについて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="8820e-114">Id 名 IsDefault</span><span class="sxs-lookup"><span data-stu-id="8820e-114">Identity Name IsDefault</span></span>

<span data-ttu-id="8820e-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="8820e-115">\-------- ---- ---------</span></span>

<span data-ttu-id="8820e-116">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="8820e-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="8820e-117">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="8820e-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="8820e-118">IsDefault プロパティが True に設定されている場合、対応するドメインが既定の SIP ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="8820e-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="8820e-119">Set-CsSipDomain コマンドレットを使用して、組織の既定の SIP ドメインを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="8820e-120">ただし、既定の SIP ドメインを削除するだけで、既定のドメインがなくなるため、単純に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8820e-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="8820e-121">前の例で示したように、fabrikam.com ドメインを削除するには、まず、既定のドメインとして na.fabrikam.com を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="8820e-122">会議の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-122">Check meeting settings</span></span>

<span data-ttu-id="8820e-123">会議の設定には、会議ポリシーの定義と、会議への匿名ユーザーの参加のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8820e-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="8820e-124">会議の構成設定を取得するには、Windows PowerShell および **get-help/csconfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8820e-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="8820e-125">たとえば、次のコマンドを実行すると、グローバルな会議の構成設定に関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="8820e-126">Get-CsMeetingConfiguration – Id "Global" 会議の構成設定をサイトスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="8820e-127">そのため、次のコマンドを使用すると、すべての会議構成設定に関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="8820e-128">このコマンドレットを実行すると、次のような情報が **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="8820e-129">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-129">Identity : Global</span></span>

<span data-ttu-id="8820e-130">PstnCallersBypassLobby: True</span><span class="sxs-lookup"><span data-stu-id="8820e-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="8820e-131">EnableAssignedConferenceType: True</span><span class="sxs-lookup"><span data-stu-id="8820e-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="8820e-132">DesignateAsPresenter: Company</span><span class="sxs-lookup"><span data-stu-id="8820e-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="8820e-133">AssignedConferenceTypeByDefault: True</span><span class="sxs-lookup"><span data-stu-id="8820e-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="8820e-134">AdmitAnonymousUsersByDefault: True</span><span class="sxs-lookup"><span data-stu-id="8820e-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="8820e-135">この場合も、 **AdmitAnonymousUsersByDefault**の最後の項目は、匿名ユーザーが会議に参加する機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="8820e-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="8820e-136">会議の構成設定を確認するときは、現在の設定を既定の対応物と比較すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="8820e-137">既定の会議構成設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8820e-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8820e-138">前のコマンドを実行すると、グローバルな会議の構成設定のメモリ内インスタンスが作成されます。これは、各プロパティの既定値を使用するインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8820e-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="8820e-139">コマンドの実行時に実際の会議構成設定は作成されません。</span><span class="sxs-lookup"><span data-stu-id="8820e-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="8820e-140">ただし、すべての既定のプロパティの値は画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="8820e-141">エッジサーバーとその設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="8820e-142">エッジサーバーの情報は、Windows PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="8820e-143">このコマンドは、組織で使用するように構成されているすべてのエッジサーバーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="8820e-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="8820e-144">返される情報には、各エッジサーバーの FQDN とポートの設定がすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="8820e-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="8820e-145">Identity: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8820e-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="8820e-146">レジストラー: レジストラー: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8820e-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="8820e-147">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="8820e-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="8820e-148">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="8820e-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="8820e-149">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="8820e-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="8820e-150">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="8820e-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="8820e-151">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="8820e-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="8820e-152">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="8820e-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="8820e-153">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="8820e-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="8820e-154">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="8820e-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="8820e-155">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="8820e-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="8820e-156">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="8820e-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="8820e-157">MediaCommunicationPortStart: 5万</span><span class="sxs-lookup"><span data-stu-id="8820e-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="8820e-158">MediaComunicationPortCount: 1万</span><span class="sxs-lookup"><span data-stu-id="8820e-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="8820e-159">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8820e-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8820e-160">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8820e-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8820e-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="8820e-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="8820e-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="8820e-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="8820e-163">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8820e-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8820e-164">DependentServiceList: {レジストラー: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="8820e-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="8820e-165">ConferencingServer: LYNC-SE</span><span class="sxs-lookup"><span data-stu-id="8820e-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="8820e-166">com、MediationServer: LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="8820e-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="8820e-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="8820e-167">fabrikam.com}</span></span>

<span data-ttu-id="8820e-168">ServiceId: fabrikam.com-EdgeServer</span><span class="sxs-lookup"><span data-stu-id="8820e-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="8820e-169">SiteId: サイト: fabrikam</span><span class="sxs-lookup"><span data-stu-id="8820e-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="8820e-170">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8820e-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8820e-171">バージョン: 5</span><span class="sxs-lookup"><span data-stu-id="8820e-171">Version : 5</span></span>

<span data-ttu-id="8820e-172">役割: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="8820e-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="8820e-173">フェデレーション設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-173">Check federation settings</span></span>

<span data-ttu-id="8820e-174">フェデレーション設定を確認します (構成されているかどうか、応答が "yes" の場合は FQDN とポート)。</span><span class="sxs-lookup"><span data-stu-id="8820e-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="8820e-175">アクセスエッジ構成設定のグローバルコレクションを使用して、フェデレーションを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="8820e-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="8820e-176">特に、次のような意味では、フェデレーションが完全にまたは何もありません。組織全体に対してフェデレーションが有効になっているか、組織全体でフェデレーションが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8820e-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="8820e-177">アクセスエッジの構成設定は、Windows PowerShell を使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8820e-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="8820e-178">そのためには、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8820e-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="8820e-179">その後、コマンドは次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="8820e-180">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-180">Identity : Global</span></span>

<span data-ttu-id="8820e-181">AllowAnonymousUsers: False</span><span class="sxs-lookup"><span data-stu-id="8820e-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="8820e-182">AllowFederatedUsers: False</span><span class="sxs-lookup"><span data-stu-id="8820e-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="8820e-183">AllowOutsideUsers: False</span><span class="sxs-lookup"><span data-stu-id="8820e-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="8820e-184">BeClearingHouse: False</span><span class="sxs-lookup"><span data-stu-id="8820e-184">BeClearingHouse : False</span></span>

<span data-ttu-id="8820e-185">EnablePartnerDiscovery: False</span><span class="sxs-lookup"><span data-stu-id="8820e-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="8820e-186">EnableArchivingDisclaimer: False</span><span class="sxs-lookup"><span data-stu-id="8820e-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="8820e-187">KeepCrlsUpToDateForPeers: True</span><span class="sxs-lookup"><span data-stu-id="8820e-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="8820e-188">MarkSourceVerifiableOnOutgoingMessages: True</span><span class="sxs-lookup"><span data-stu-id="8820e-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="8820e-189">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="8820e-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="8820e-190">RoutingMethod: Usednssrvrouting は、</span><span class="sxs-lookup"><span data-stu-id="8820e-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="8820e-191">**AllowFederatedUsers**プロパティが True に設定されている場合は、フェデレーションが組織で有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8820e-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="8820e-192">( **AllowFederatedUsers** を True に設定することも、分割ドメインのシナリオでは、オンプレミスのユーザーがクラウド内のユーザーとシームレスに通信できることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="8820e-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="8820e-193">エッジサーバーの FQDN およびポート設定を取得するには、前のタスク (エッジサーバーとその設定) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="8820e-194">グローバルスコープでフェデレーションを有効にすることは、ユーザーがフェデレーションユーザーと通信できる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8820e-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="8820e-195">個々のユーザーがフェデレーションユーザーと実際に通信できるかどうかを判断するには、そのユーザーに割り当てられた外部ユーザーアクセスポリシーを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="8820e-196">外部ユーザーアクセス情報は、Windows PowerShell を使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8820e-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="8820e-197">たとえば、次のコマンドを実行すると、グローバル外部ユーザーアクセスポリシーの情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="8820e-198">このコマンドは、すべての外部ユーザーアクセスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="8820e-199">返される情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8820e-199">The returned information will resemble this:</span></span>

<span data-ttu-id="8820e-200">Identity: False</span><span class="sxs-lookup"><span data-stu-id="8820e-200">Identity : False</span></span>

<span data-ttu-id="8820e-201">Description</span><span class="sxs-lookup"><span data-stu-id="8820e-201">Description :</span></span>

<span data-ttu-id="8820e-202">EnableFederationAccess: False</span><span class="sxs-lookup"><span data-stu-id="8820e-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="8820e-203">EnablePublicCloudAccess: False</span><span class="sxs-lookup"><span data-stu-id="8820e-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="8820e-204">EnablePublicCloudAccessAudioVideoAccess: False</span><span class="sxs-lookup"><span data-stu-id="8820e-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="8820e-205">EnableOutsideAccess: False</span><span class="sxs-lookup"><span data-stu-id="8820e-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="8820e-206">**EnableFederationAccess**が True に設定されている場合、特定のポリシーによって管理されるユーザーは、フェデレーションユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="8820e-207">アーカイブ設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-207">Check archiving settings</span></span>

<span data-ttu-id="8820e-208">内部およびフェデレーション通信のアーカイブ設定を確認します。内部および外部アーカイブの設定を確認する前に、アーカイブが有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="8820e-209">アーカイブ構成設定は、Windows PowerShell と Get-CsArchivingConfiguration コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="8820e-210">アーカイブ設定は、サイトスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="8820e-211">すべてのアーカイブ設定に関する情報を戻すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8820e-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="8820e-212">Get-CsArchivingConfiguration コマンドレットは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="8820e-213">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-213">Identity : Global</span></span>

<span data-ttu-id="8820e-214">EnableArchiving: False</span><span class="sxs-lookup"><span data-stu-id="8820e-214">EnableArchiving : False</span></span>

<span data-ttu-id="8820e-215">EnablePurging: False</span><span class="sxs-lookup"><span data-stu-id="8820e-215">EnablePurging : False</span></span>

<span data-ttu-id="8820e-216">PurgeExportedArchivesOnly: False</span><span class="sxs-lookup"><span data-stu-id="8820e-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="8820e-217">Blockonアーカイブエラー: False</span><span class="sxs-lookup"><span data-stu-id="8820e-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="8820e-218">KeepArchivingDataForDays:14</span><span class="sxs-lookup"><span data-stu-id="8820e-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="8820e-219">で purgehourofday: 2</span><span class="sxs-lookup"><span data-stu-id="8820e-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="8820e-220">ArchiveDuplicateMessages: True</span><span class="sxs-lookup"><span data-stu-id="8820e-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="8820e-221">CachePurgingInterval:24</span><span class="sxs-lookup"><span data-stu-id="8820e-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="8820e-222">EnableArchiving プロパティが False に設定されている場合は、通信セッションがアーカイブされないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8820e-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="8820e-223">インスタントメッセージングセッションのみをアーカイブする場合は、次のようなコマンドを使用して IM セッションのアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8820e-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="8820e-224">会議セッションおよびインスタントメッセージングセッションをアーカイブするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8820e-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="8820e-225">現在のアーカイブ設定と既定の設定を比較したい場合は、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8820e-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8820e-226">このコマンドは、グローバルアーカイブ構成設定のメモリ内インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8820e-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="8820e-227">これは、Lync Server で使用される設定の実際のコレクションではありません。</span><span class="sxs-lookup"><span data-stu-id="8820e-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="8820e-228">ただし、すべてのアーカイブ構成プロパティの既定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="8820e-229">また、次のコマンドを使用して、アーカイブサーバーの FQDN を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="8820e-230">アーカイブが有効になっていることを確認したら、アーカイブポリシーを表示して、内部通信セッションと外部通信セッションがアーカイブされているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="8820e-231">アーカイブポリシー情報は Get-CsArchivingPolicy コマンドレットを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="8820e-232">たとえば、次のコマンドを実行すると、グローバルアーカイブポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="8820e-233">アーカイブポリシーは、サイトとユーザーごとのスコープで構成することもできます。また、このコマンドを使用して、すべてのアーカイブポリシーに関する情報を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="8820e-234">Get-CsArchivingPolicy から受け取る情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8820e-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="8820e-235">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-235">Identity : Global</span></span>

<span data-ttu-id="8820e-236">Description</span><span class="sxs-lookup"><span data-stu-id="8820e-236">Description :</span></span>

<span data-ttu-id="8820e-237">アーカイブ内部: False</span><span class="sxs-lookup"><span data-stu-id="8820e-237">ArchiveInternal : False</span></span>

<span data-ttu-id="8820e-238">アーカイブ外部: False</span><span class="sxs-lookup"><span data-stu-id="8820e-238">ArchiveExternal : False</span></span>

<span data-ttu-id="8820e-239">既定では、アーカイブポリシーで内部と外部の両方のアーカイブが無効になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="8820e-240">CDR の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-240">Check CDR settings</span></span>

<span data-ttu-id="8820e-241">ピアツーピア、電話会議、音声通話詳細記録の通話詳細記録 (CDR) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="8820e-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="8820e-242">CDR の設定の詳細については、Set-cscdrconfiguration コマンドレットを使用して **取得** できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="8820e-243">たとえば、次のコマンドを実行すると、CDR 構成設定のグローバルコレクションに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="8820e-244">また、CDR をサイトスコープで構成することもできるので、次のコマンドを実行することもできます。このコマンドは、すべての CDR 構成設定に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="8820e-245">Get-CsCdrConfiguration コマンドレットは、CDR 構成設定のコレクションごとに、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="8820e-246">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-246">Identity : Global</span></span>

<span data-ttu-id="8820e-247">EnableCDR: True</span><span class="sxs-lookup"><span data-stu-id="8820e-247">EnableCDR : True</span></span>

<span data-ttu-id="8820e-248">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="8820e-248">EnablePurging : True</span></span>

<span data-ttu-id="8820e-249">KeepCallDetailForDays:60</span><span class="sxs-lookup"><span data-stu-id="8820e-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="8820e-250">KeepErrorReportForDays:60</span><span class="sxs-lookup"><span data-stu-id="8820e-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="8820e-251">で purgehourofday: 2</span><span class="sxs-lookup"><span data-stu-id="8820e-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="8820e-252">Get-CsQoEConfiguration コマンドレットを使用して、QoE 監視について同様の情報を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8820e-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="8820e-253">たとえば、次のコマンドを実行すると、QoE 構成設定のグローバルコレクションに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="8820e-254">この情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8820e-254">That information will resemble this:</span></span>

<span data-ttu-id="8820e-255">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-255">Identity : Global</span></span>

<span data-ttu-id="8820e-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="8820e-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="8820e-257">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="8820e-257">EnablePurging : True</span></span>

<span data-ttu-id="8820e-258">KeepQoEDataForDays:60</span><span class="sxs-lookup"><span data-stu-id="8820e-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="8820e-259">で purgehourofday: 1</span><span class="sxs-lookup"><span data-stu-id="8820e-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="8820e-260">EnableExternalConsumer: False</span><span class="sxs-lookup"><span data-stu-id="8820e-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="8820e-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="8820e-261">ExternalConsumerName :</span></span>

<span data-ttu-id="8820e-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="8820e-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="8820e-263">EnableQoE: True</span><span class="sxs-lookup"><span data-stu-id="8820e-263">EnableQoE : True</span></span>

<span data-ttu-id="8820e-264">現在の CDR 設定を既定の CDR 設定と比較する場合は、次のコマンドを実行すると、既定値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8820e-265">同様に、QoE 監視の既定値は、次のコマンドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8820e-266">また、次のコマンドを実行して、監視サーバーの FQDN を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="8820e-267">音声設定の確認</span><span class="sxs-lookup"><span data-stu-id="8820e-267">Check voice settings</span></span>

<span data-ttu-id="8820e-268">通常、管理者にとって重要な音声設定は、音声ポリシーと音声ルートに含まれています。音声ポリシーには、個々のユーザーに公開される機能を決定する設定 (通話を転送または転送する機能など) が含まれますが、音声ルートでは通話が PSTN を介してルーティングされる方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="8820e-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="8820e-269">音声ポリシー情報は、Windows PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="8820e-270">たとえば、次のコマンドを実行すると、グローバル音声ポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="8820e-271">このコマンドを実行すると、組織で使用するように構成されているすべての音声ポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="8820e-272">Get-CsVoicePolicy コマンドレットによって返される情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8820e-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="8820e-273">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-273">Identity : Global</span></span>

<span data-ttu-id="8820e-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="8820e-274">PstnUsages : {}</span></span>

<span data-ttu-id="8820e-275">Description</span><span class="sxs-lookup"><span data-stu-id="8820e-275">Description :</span></span>

<span data-ttu-id="8820e-276">AllowSimulRing: True</span><span class="sxs-lookup"><span data-stu-id="8820e-276">AllowSimulRing : True</span></span>

<span data-ttu-id="8820e-277">AllowCallForwarding: True</span><span class="sxs-lookup"><span data-stu-id="8820e-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="8820e-278">AllowPSTNReRouting: True</span><span class="sxs-lookup"><span data-stu-id="8820e-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="8820e-279">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="8820e-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="8820e-280">EnableDelegation: True</span><span class="sxs-lookup"><span data-stu-id="8820e-280">EnableDelegation : True</span></span>

<span data-ttu-id="8820e-281">EnableTeamCall: True</span><span class="sxs-lookup"><span data-stu-id="8820e-281">EnableTeamCall : True</span></span>

<span data-ttu-id="8820e-282">EnableCallTransfer: True</span><span class="sxs-lookup"><span data-stu-id="8820e-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="8820e-283">EnableCallPark: False</span><span class="sxs-lookup"><span data-stu-id="8820e-283">EnableCallPark : False</span></span>

<span data-ttu-id="8820e-284">EnableMaliciousCallTracing: False</span><span class="sxs-lookup"><span data-stu-id="8820e-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="8820e-285">EnableBWPolicyOverride: False</span><span class="sxs-lookup"><span data-stu-id="8820e-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="8820e-286">PreventPSTNTollBypass: False</span><span class="sxs-lookup"><span data-stu-id="8820e-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="8820e-287">音声ポリシーのサブセットを返すクエリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="8820e-288">たとえば、次のコマンドは、着信転送が許可されているすべての音声ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="8820e-289">このコマンドは、着信転送が許可されていないすべての音声ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="8820e-290">Windows PowerShell では、Get-CsVoiceRouting コマンドレットを使用して、音声ルートに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8820e-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="8820e-291">このコマンドは、すべての音声ルートについて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="8820e-292">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="8820e-292">Identity : LocalRoute</span></span>

<span data-ttu-id="8820e-293">優先度: 0</span><span class="sxs-lookup"><span data-stu-id="8820e-293">Priority : 0</span></span>

<span data-ttu-id="8820e-294">Description</span><span class="sxs-lookup"><span data-stu-id="8820e-294">Description :</span></span>

<span data-ttu-id="8820e-295">数字パターン: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="8820e-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="8820e-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="8820e-296">PstnUsages : {}</span></span>

<span data-ttu-id="8820e-297">PstnGatewayList {}</span><span class="sxs-lookup"><span data-stu-id="8820e-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="8820e-298">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="8820e-298">Name : LocalRoute</span></span>

<span data-ttu-id="8820e-299">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="8820e-299">SuppressCallerId :</span></span>

<span data-ttu-id="8820e-300">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="8820e-300">AlternateCallerId :</span></span>

<span data-ttu-id="8820e-301">Lync Server を使用すると、PSTN を使用しない音声ルートを作成し、PSTN ゲートウェイを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8820e-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="8820e-302">ただし、この2つのプロパティ値が構成されていない音声ルート経由で実際に通話をルーティングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8820e-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="8820e-303">そのため、このコマンドを定期的に実行することが有益な場合があります。このコマンドは、PSTN を使用していないボイスルートの id を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="8820e-304">同様に、次のコマンドは、PSTN ゲートウェイを持たないように構成されていないすべての音声ルートの id を返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="8820e-305">電話会議アテンダントの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8820e-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="8820e-306">PSTN ダイヤルイン会議の会議アテンダント設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="8820e-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="8820e-307">電話会議アテンダントの設定は、 **set-csdialinconferencingconfiguration** コマンドレットを使用してのみ取得できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="8820e-308">これらの設定は、Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8820e-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="8820e-309">会議アテンダントの設定を表示するには、次のような Windows PowerShell コマンドを使用します。これは、会議アテンダント設定のグローバルコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="8820e-310">会議アテンダントの設定は、サイトスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8820e-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="8820e-311">会議アテンダントのすべての設定に関する情報を戻すには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8820e-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="8820e-312">Get-CsDialInConferencingConfiguration コマンドレットは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="8820e-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="8820e-313">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="8820e-313">Identity : Global</span></span>

<span data-ttu-id="8820e-314">Entryexitアナウンス ementstype: usentry</span><span class="sxs-lookup"><span data-stu-id="8820e-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="8820e-315">EnableNameRecording: True</span><span class="sxs-lookup"><span data-stu-id="8820e-315">EnableNameRecording : True</span></span>

<span data-ttu-id="8820e-316">EntryExitAnnouncementsEnabledByDefault: False</span><span class="sxs-lookup"><span data-stu-id="8820e-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="8820e-317">EntryExitAnnouncementsEnabledByDefault が False に設定されている場合、会議アナウンスは無効になります。</span><span class="sxs-lookup"><span data-stu-id="8820e-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="8820e-318">Entry と exit アナウンスを有効にするには、次のような Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8820e-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8820e-319">関連項目</span><span class="sxs-lookup"><span data-stu-id="8820e-319">See Also</span></span>


[<span data-ttu-id="8820e-320">New-cssipdomain</span><span class="sxs-lookup"><span data-stu-id="8820e-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="8820e-321">-Cs会議構成の取得</span><span class="sxs-lookup"><span data-stu-id="8820e-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="8820e-322">取得-CsService</span><span class="sxs-lookup"><span data-stu-id="8820e-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="8820e-323">Set-csaccessedgeconfiguration</span><span class="sxs-lookup"><span data-stu-id="8820e-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="8820e-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8820e-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="8820e-325">Set-csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="8820e-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="8820e-326">Set-cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="8820e-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="8820e-327">取得-CsQoEConfiguration 場合</span><span class="sxs-lookup"><span data-stu-id="8820e-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="8820e-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="8820e-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="8820e-329">Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="8820e-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="8820e-330">Set-csdialinconferencingconfiguration</span><span class="sxs-lookup"><span data-stu-id="8820e-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

