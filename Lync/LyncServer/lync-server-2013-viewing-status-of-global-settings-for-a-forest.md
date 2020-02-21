---
title: 'Lync Server 2013: フォレストのグローバル設定の状態を表示する'
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
ms.openlocfilehash: ab574067b05b494601e0dd769003cb01904c52bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="da00b-102">Lync Server 2013 のフォレストのグローバル設定の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="da00b-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da00b-103">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="da00b-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="da00b-104">管理者は、Lync Server 2013 展開のグローバル設定を毎月確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da00b-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="da00b-105">目的は、一連の既知の構成に対して実装済みの設定を確認することです。基準構成は、設定が有効であることを保証し、ベースラインのドキュメントを更新する必要があるかどうかを判断するためのものです。</span><span class="sxs-lookup"><span data-stu-id="da00b-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="da00b-106">グローバル設定の変更は、新しい設定を文書化することを含める必要がある変更管理プロセスによって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da00b-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="da00b-107">次のセクションでは、確認が必要なグローバル設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="da00b-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="da00b-108">全般設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-108">Check general settings</span></span>

<span data-ttu-id="da00b-109">Lync Server 2013 でサポートされているセッション開始プロトコル (SIP) ドメインなど、全般設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="da00b-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="da00b-110">SIP ドメイン情報は、Windows PowerShell と**new-cssipdomain**コマンドレットを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="da00b-111">この情報を取得するには`Get-CsSipDomain` 、Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da00b-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="da00b-112">New-cssipdomain は、認証されたすべての SIP ドメインについて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="da00b-113">Id 名 IsDefault</span><span class="sxs-lookup"><span data-stu-id="da00b-113">Identity Name IsDefault</span></span>

<span data-ttu-id="da00b-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="da00b-114">\-------- ---- ---------</span></span>

<span data-ttu-id="da00b-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="da00b-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="da00b-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="da00b-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="da00b-117">IsDefault プロパティが True に設定されている場合、対応するドメインが既定の SIP ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="da00b-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="da00b-118">New-cssipdomain コマンドレットを使用して、組織の既定の SIP ドメインを変更できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="da00b-119">ただし、既定の SIP ドメインを削除するだけで、既定のドメインがなくなるため、単純に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="da00b-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="da00b-120">前の例で示したように、fabrikam.com ドメインを削除するには、まず、既定のドメインとして na.fabrikam.com を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da00b-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="da00b-121">会議の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-121">Check meeting settings</span></span>

<span data-ttu-id="da00b-122">会議の設定には、会議ポリシーの定義と、会議への匿名ユーザーの参加のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="da00b-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="da00b-123">会議の構成設定を取得するには、Windows PowerShell および**get-help/csconfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="da00b-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="da00b-124">たとえば、次のコマンドを実行すると、グローバルな会議の構成設定に関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="da00b-125">Get-help-Csconfiguration-Id "Global" 会議の構成設定をサイトスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="da00b-126">そのため、次のコマンドを使用すると、すべての会議構成設定に関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="da00b-127">このコマンドレットを実行すると、次のような情報が**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="da00b-128">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-128">Identity : Global</span></span>

<span data-ttu-id="da00b-129">PstnCallersBypassLobby: True</span><span class="sxs-lookup"><span data-stu-id="da00b-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="da00b-130">EnableAssignedConferenceType: True</span><span class="sxs-lookup"><span data-stu-id="da00b-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="da00b-131">DesignateAsPresenter: Company</span><span class="sxs-lookup"><span data-stu-id="da00b-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="da00b-132">AssignedConferenceTypeByDefault: True</span><span class="sxs-lookup"><span data-stu-id="da00b-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="da00b-133">AdmitAnonymousUsersByDefault: True</span><span class="sxs-lookup"><span data-stu-id="da00b-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="da00b-134">この場合も、 **AdmitAnonymousUsersByDefault**の最後の項目は、匿名ユーザーが会議に参加する機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="da00b-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="da00b-135">会議の構成設定を確認するときは、現在の設定を既定の対応物と比較すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="da00b-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="da00b-136">既定の会議構成設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da00b-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="da00b-137">前のコマンドを実行すると、グローバルな会議の構成設定のメモリ内インスタンスが作成されます。これは、各プロパティの既定値を使用するインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="da00b-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="da00b-138">コマンドの実行時に実際の会議構成設定は作成されません。</span><span class="sxs-lookup"><span data-stu-id="da00b-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="da00b-139">ただし、すべての既定のプロパティの値は画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="da00b-140">エッジサーバーとその設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="da00b-141">エッジサーバーの情報は、Windows PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="da00b-142">このコマンドは、組織で使用するように構成されているすべてのエッジサーバーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="da00b-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="da00b-143">返される情報には、各エッジサーバーの FQDN とポートの設定がすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="da00b-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="da00b-144">Identity: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="da00b-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="da00b-145">レジストラー: レジストラー: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="da00b-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="da00b-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="da00b-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="da00b-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="da00b-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="da00b-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="da00b-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="da00b-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="da00b-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="da00b-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="da00b-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="da00b-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="da00b-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="da00b-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="da00b-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="da00b-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="da00b-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="da00b-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="da00b-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="da00b-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="da00b-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="da00b-156">MediaCommunicationPortStart: 5万</span><span class="sxs-lookup"><span data-stu-id="da00b-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="da00b-157">MediaComunicationPortCount: 1万</span><span class="sxs-lookup"><span data-stu-id="da00b-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="da00b-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="da00b-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="da00b-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="da00b-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="da00b-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="da00b-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="da00b-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="da00b-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="da00b-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="da00b-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="da00b-163">DependentServiceList: {レジストラー: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="da00b-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="da00b-164">ConferencingServer: LYNC-SE</span><span class="sxs-lookup"><span data-stu-id="da00b-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="da00b-165">com、MediationServer: LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="da00b-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="da00b-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="da00b-166">fabrikam.com}</span></span>

<span data-ttu-id="da00b-167">ServiceId: fabrikam.com-EdgeServer</span><span class="sxs-lookup"><span data-stu-id="da00b-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="da00b-168">SiteId: サイト: fabrikam</span><span class="sxs-lookup"><span data-stu-id="da00b-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="da00b-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="da00b-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="da00b-170">バージョン: 5</span><span class="sxs-lookup"><span data-stu-id="da00b-170">Version : 5</span></span>

<span data-ttu-id="da00b-171">役割: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="da00b-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="da00b-172">フェデレーション設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-172">Check federation settings</span></span>

<span data-ttu-id="da00b-173">フェデレーション設定を確認します (構成されているかどうか、応答が "yes" の場合は FQDN とポート)。</span><span class="sxs-lookup"><span data-stu-id="da00b-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="da00b-174">アクセスエッジ構成設定のグローバルコレクションを使用して、フェデレーションを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="da00b-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="da00b-175">特に、次のような意味では、フェデレーションが完全にまたは何もありません。組織全体に対してフェデレーションが有効になっているか、組織全体でフェデレーションが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="da00b-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="da00b-176">アクセスエッジの構成設定は、Windows PowerShell を使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="da00b-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="da00b-177">そのためには、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da00b-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="da00b-178">その後、コマンドは次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="da00b-179">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-179">Identity : Global</span></span>

<span data-ttu-id="da00b-180">AllowAnonymousUsers: False</span><span class="sxs-lookup"><span data-stu-id="da00b-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="da00b-181">AllowFederatedUsers: False</span><span class="sxs-lookup"><span data-stu-id="da00b-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="da00b-182">AllowOutsideUsers: False</span><span class="sxs-lookup"><span data-stu-id="da00b-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="da00b-183">BeClearingHouse: False</span><span class="sxs-lookup"><span data-stu-id="da00b-183">BeClearingHouse : False</span></span>

<span data-ttu-id="da00b-184">EnablePartnerDiscovery: False</span><span class="sxs-lookup"><span data-stu-id="da00b-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="da00b-185">EnableArchivingDisclaimer: False</span><span class="sxs-lookup"><span data-stu-id="da00b-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="da00b-186">KeepCrlsUpToDateForPeers: True</span><span class="sxs-lookup"><span data-stu-id="da00b-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="da00b-187">MarkSourceVerifiableOnOutgoingMessages: True</span><span class="sxs-lookup"><span data-stu-id="da00b-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="da00b-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="da00b-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="da00b-189">RoutingMethod: Usednssrvrouting は、</span><span class="sxs-lookup"><span data-stu-id="da00b-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="da00b-190">**AllowFederatedUsers**プロパティが True に設定されている場合は、フェデレーションが組織で有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="da00b-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="da00b-191">( **AllowFederatedUsers**を True に設定することも、分割ドメインのシナリオでは、オンプレミスのユーザーがクラウド内のユーザーとシームレスに通信できることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="da00b-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="da00b-192">エッジサーバーの FQDN およびポート設定を取得するには、前のタスク (エッジサーバーとその設定) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da00b-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="da00b-193">グローバルスコープでフェデレーションを有効にすることは、ユーザーがフェデレーションユーザーと通信できる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="da00b-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="da00b-194">個々のユーザーがフェデレーションユーザーと実際に通信できるかどうかを判断するには、そのユーザーに割り当てられた外部ユーザーアクセスポリシーを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da00b-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="da00b-195">外部ユーザーアクセス情報は、Windows PowerShell を使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="da00b-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="da00b-196">たとえば、次のコマンドを実行すると、グローバル外部ユーザーアクセスポリシーの情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="da00b-197">このコマンドは、すべての外部ユーザーアクセスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="da00b-198">返される情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da00b-198">The returned information will resemble this:</span></span>

<span data-ttu-id="da00b-199">Identity: False</span><span class="sxs-lookup"><span data-stu-id="da00b-199">Identity : False</span></span>

<span data-ttu-id="da00b-200">Description</span><span class="sxs-lookup"><span data-stu-id="da00b-200">Description :</span></span>

<span data-ttu-id="da00b-201">EnableFederationAccess: False</span><span class="sxs-lookup"><span data-stu-id="da00b-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="da00b-202">EnablePublicCloudAccess: False</span><span class="sxs-lookup"><span data-stu-id="da00b-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="da00b-203">EnablePublicCloudAccessAudioVideoAccess: False</span><span class="sxs-lookup"><span data-stu-id="da00b-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="da00b-204">EnableOutsideAccess: False</span><span class="sxs-lookup"><span data-stu-id="da00b-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="da00b-205">**EnableFederationAccess**が True に設定されている場合、特定のポリシーによって管理されるユーザーは、フェデレーションユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="da00b-206">アーカイブ設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-206">Check archiving settings</span></span>

<span data-ttu-id="da00b-207">内部およびフェデレーション通信のアーカイブ設定を確認します。内部および外部アーカイブの設定を確認する前に、アーカイブが有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da00b-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="da00b-208">アーカイブ構成設定は、Windows PowerShell と Set-csarchivingconfiguration コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="da00b-209">アーカイブ設定は、サイトスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="da00b-210">すべてのアーカイブ設定に関する情報を戻すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da00b-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="da00b-211">Set-csarchivingconfiguration コマンドレットは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="da00b-212">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-212">Identity : Global</span></span>

<span data-ttu-id="da00b-213">EnableArchiving: False</span><span class="sxs-lookup"><span data-stu-id="da00b-213">EnableArchiving : False</span></span>

<span data-ttu-id="da00b-214">EnablePurging: False</span><span class="sxs-lookup"><span data-stu-id="da00b-214">EnablePurging : False</span></span>

<span data-ttu-id="da00b-215">PurgeExportedArchivesOnly: False</span><span class="sxs-lookup"><span data-stu-id="da00b-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="da00b-216">Blockonアーカイブエラー: False</span><span class="sxs-lookup"><span data-stu-id="da00b-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="da00b-217">KeepArchivingDataForDays:14</span><span class="sxs-lookup"><span data-stu-id="da00b-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="da00b-218">で purgehourofday: 2</span><span class="sxs-lookup"><span data-stu-id="da00b-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="da00b-219">ArchiveDuplicateMessages: True</span><span class="sxs-lookup"><span data-stu-id="da00b-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="da00b-220">CachePurgingInterval:24</span><span class="sxs-lookup"><span data-stu-id="da00b-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="da00b-221">EnableArchiving プロパティが False に設定されている場合は、通信セッションがアーカイブされないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="da00b-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="da00b-222">インスタントメッセージングセッションのみをアーカイブする場合は、次のようなコマンドを使用して IM セッションのアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="da00b-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="da00b-223">会議セッションおよびインスタントメッセージングセッションをアーカイブするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da00b-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="da00b-224">現在のアーカイブ設定と既定の設定を比較したい場合は、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da00b-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="da00b-225">このコマンドは、グローバルアーカイブ構成設定のメモリ内インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="da00b-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="da00b-226">これは、Lync Server で使用される設定の実際のコレクションではありません。</span><span class="sxs-lookup"><span data-stu-id="da00b-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="da00b-227">ただし、すべてのアーカイブ構成プロパティの既定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="da00b-228">また、次のコマンドを使用して、アーカイブサーバーの FQDN を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="da00b-229">アーカイブが有効になっていることを確認したら、アーカイブポリシーを表示して、内部通信セッションと外部通信セッションがアーカイブされているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="da00b-230">アーカイブポリシー情報は、Grant-csarchivingpolicy コマンドレットを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="da00b-231">たとえば、次のコマンドを実行すると、グローバルアーカイブポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="da00b-232">アーカイブポリシーは、サイトとユーザーごとのスコープで構成することもできます。また、このコマンドを使用して、すべてのアーカイブポリシーに関する情報を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="da00b-233">Grant-csarchivingpolicy から受け取る情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da00b-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="da00b-234">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-234">Identity : Global</span></span>

<span data-ttu-id="da00b-235">Description</span><span class="sxs-lookup"><span data-stu-id="da00b-235">Description :</span></span>

<span data-ttu-id="da00b-236">アーカイブ内部: False</span><span class="sxs-lookup"><span data-stu-id="da00b-236">ArchiveInternal : False</span></span>

<span data-ttu-id="da00b-237">アーカイブ外部: False</span><span class="sxs-lookup"><span data-stu-id="da00b-237">ArchiveExternal : False</span></span>

<span data-ttu-id="da00b-238">既定では、アーカイブポリシーで内部と外部の両方のアーカイブが無効になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="da00b-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="da00b-239">CDR の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-239">Check CDR settings</span></span>

<span data-ttu-id="da00b-240">ピアツーピア、電話会議、音声通話詳細記録の通話詳細記録 (CDR) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="da00b-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="da00b-241">CDR の設定の詳細については、Set-cscdrconfiguration コマンドレットを使用して**取得**できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="da00b-242">たとえば、次のコマンドを実行すると、CDR 構成設定のグローバルコレクションに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="da00b-243">また、CDR をサイトスコープで構成することもできるので、次のコマンドを実行することもできます。このコマンドは、すべての CDR 構成設定に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="da00b-244">Set-cscdrconfiguration コマンドレットは、CDR 構成設定のコレクションごとに、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="da00b-245">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-245">Identity : Global</span></span>

<span data-ttu-id="da00b-246">EnableCDR: True</span><span class="sxs-lookup"><span data-stu-id="da00b-246">EnableCDR : True</span></span>

<span data-ttu-id="da00b-247">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="da00b-247">EnablePurging : True</span></span>

<span data-ttu-id="da00b-248">KeepCallDetailForDays:60</span><span class="sxs-lookup"><span data-stu-id="da00b-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="da00b-249">KeepErrorReportForDays:60</span><span class="sxs-lookup"><span data-stu-id="da00b-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="da00b-250">で purgehourofday: 2</span><span class="sxs-lookup"><span data-stu-id="da00b-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="da00b-251">QoE 監視についても同様の情報を返すことができます。そのためには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="da00b-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="da00b-252">たとえば、次のコマンドを実行すると、QoE 構成設定のグローバルコレクションに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="da00b-253">この情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da00b-253">That information will resemble this:</span></span>

<span data-ttu-id="da00b-254">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-254">Identity : Global</span></span>

<span data-ttu-id="da00b-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="da00b-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="da00b-256">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="da00b-256">EnablePurging : True</span></span>

<span data-ttu-id="da00b-257">KeepQoEDataForDays:60</span><span class="sxs-lookup"><span data-stu-id="da00b-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="da00b-258">で purgehourofday: 1</span><span class="sxs-lookup"><span data-stu-id="da00b-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="da00b-259">EnableExternalConsumer: False</span><span class="sxs-lookup"><span data-stu-id="da00b-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="da00b-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="da00b-260">ExternalConsumerName :</span></span>

<span data-ttu-id="da00b-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="da00b-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="da00b-262">EnableQoE: True</span><span class="sxs-lookup"><span data-stu-id="da00b-262">EnableQoE : True</span></span>

<span data-ttu-id="da00b-263">現在の CDR 設定を既定の CDR 設定と比較する場合は、次のコマンドを実行すると、既定値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="da00b-264">同様に、QoE 監視の既定値は、次のコマンドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="da00b-265">また、次のコマンドを実行して、監視サーバーの FQDN を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="da00b-266">音声設定の確認</span><span class="sxs-lookup"><span data-stu-id="da00b-266">Check voice settings</span></span>

<span data-ttu-id="da00b-267">通常、管理者にとって重要な音声設定は、音声ポリシーと音声ルートに含まれています。音声ポリシーには、個々のユーザーに公開する機能 (通話の転送や転送など) を決定する設定が含まれています。音声ルートは、(および if) 通話が PSTN を介してルーティングされる方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="da00b-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="da00b-268">音声ポリシー情報は、Windows PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="da00b-269">たとえば、次のコマンドを実行すると、グローバル音声ポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="da00b-270">このコマンドを実行すると、組織で使用するように構成されているすべての音声ポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="da00b-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="da00b-271">Set-csvoicepolicy コマンドレットによって返される情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da00b-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="da00b-272">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-272">Identity : Global</span></span>

<span data-ttu-id="da00b-273">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="da00b-273">PstnUsages : {}</span></span>

<span data-ttu-id="da00b-274">Description</span><span class="sxs-lookup"><span data-stu-id="da00b-274">Description :</span></span>

<span data-ttu-id="da00b-275">AllowSimulRing: True</span><span class="sxs-lookup"><span data-stu-id="da00b-275">AllowSimulRing : True</span></span>

<span data-ttu-id="da00b-276">AllowCallForwarding: True</span><span class="sxs-lookup"><span data-stu-id="da00b-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="da00b-277">AllowPSTNReRouting: True</span><span class="sxs-lookup"><span data-stu-id="da00b-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="da00b-278">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="da00b-279">EnableDelegation: True</span><span class="sxs-lookup"><span data-stu-id="da00b-279">EnableDelegation : True</span></span>

<span data-ttu-id="da00b-280">EnableTeamCall: True</span><span class="sxs-lookup"><span data-stu-id="da00b-280">EnableTeamCall : True</span></span>

<span data-ttu-id="da00b-281">EnableCallTransfer: True</span><span class="sxs-lookup"><span data-stu-id="da00b-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="da00b-282">EnableCallPark: False</span><span class="sxs-lookup"><span data-stu-id="da00b-282">EnableCallPark : False</span></span>

<span data-ttu-id="da00b-283">EnableMaliciousCallTracing: False</span><span class="sxs-lookup"><span data-stu-id="da00b-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="da00b-284">EnableBWPolicyOverride: False</span><span class="sxs-lookup"><span data-stu-id="da00b-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="da00b-285">PreventPSTNTollBypass: False</span><span class="sxs-lookup"><span data-stu-id="da00b-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="da00b-286">音声ポリシーのサブセットを返すクエリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="da00b-287">たとえば、次のコマンドは、着信転送が許可されているすべての音声ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="da00b-288">このコマンドは、着信転送が許可されていないすべての音声ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="da00b-289">Windows PowerShell では、CsVoiceRouting コマンドレットを使用して、音声ルートに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="da00b-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="da00b-290">このコマンドは、すべての音声ルートについて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="da00b-291">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="da00b-291">Identity : LocalRoute</span></span>

<span data-ttu-id="da00b-292">優先度: 0</span><span class="sxs-lookup"><span data-stu-id="da00b-292">Priority : 0</span></span>

<span data-ttu-id="da00b-293">Description</span><span class="sxs-lookup"><span data-stu-id="da00b-293">Description :</span></span>

<span data-ttu-id="da00b-294">数字パターン: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="da00b-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="da00b-295">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="da00b-295">PstnUsages : {}</span></span>

<span data-ttu-id="da00b-296">PstnGatewayList{}</span><span class="sxs-lookup"><span data-stu-id="da00b-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="da00b-297">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="da00b-297">Name : LocalRoute</span></span>

<span data-ttu-id="da00b-298">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="da00b-298">SuppressCallerId :</span></span>

<span data-ttu-id="da00b-299">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="da00b-299">AlternateCallerId :</span></span>

<span data-ttu-id="da00b-300">Lync Server を使用すると、PSTN を使用しない音声ルートを作成し、PSTN ゲートウェイを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="da00b-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="da00b-301">ただし、この2つのプロパティ値が構成されていない音声ルート経由で実際に通話をルーティングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="da00b-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="da00b-302">そのため、このコマンドを定期的に実行することが有益な場合があります。このコマンドは、PSTN を使用していないボイスルートの id を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="da00b-303">同様に、次のコマンドは、PSTN ゲートウェイを持たないように構成されていないすべての音声ルートの id を返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="da00b-304">電話会議アテンダントの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="da00b-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="da00b-305">PSTN ダイヤルイン会議の会議アテンダント設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="da00b-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="da00b-306">電話会議アテンダントの設定は、 **set-csdialinconferencingconfiguration**コマンドレットを使用してのみ取得できます。</span><span class="sxs-lookup"><span data-stu-id="da00b-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="da00b-307">これらの設定は、Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="da00b-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="da00b-308">会議アテンダントの設定を表示するには、次のような Windows PowerShell コマンドを使用します。これは、会議アテンダント設定のグローバルコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="da00b-309">会議アテンダントの設定は、サイトスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da00b-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="da00b-310">会議アテンダントのすべての設定に関する情報を戻すには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="da00b-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="da00b-311">Set-csdialinconferencingconfiguration コマンドレットは、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="da00b-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="da00b-312">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="da00b-312">Identity : Global</span></span>

<span data-ttu-id="da00b-313">Entryexitアナウンス ementstype: usentry</span><span class="sxs-lookup"><span data-stu-id="da00b-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="da00b-314">EnableNameRecording: True</span><span class="sxs-lookup"><span data-stu-id="da00b-314">EnableNameRecording : True</span></span>

<span data-ttu-id="da00b-315">EntryExitAnnouncementsEnabledByDefault: False</span><span class="sxs-lookup"><span data-stu-id="da00b-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="da00b-316">EntryExitAnnouncementsEnabledByDefault が False に設定されている場合、会議アナウンスは無効になります。</span><span class="sxs-lookup"><span data-stu-id="da00b-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="da00b-317">Entry と exit アナウンスを有効にするには、次のような Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da00b-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da00b-318">関連項目</span><span class="sxs-lookup"><span data-stu-id="da00b-318">See Also</span></span>


[<span data-ttu-id="da00b-319">New-cssipdomain</span><span class="sxs-lookup"><span data-stu-id="da00b-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="da00b-320">-Cs会議構成の取得</span><span class="sxs-lookup"><span data-stu-id="da00b-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="da00b-321">取得-CsService</span><span class="sxs-lookup"><span data-stu-id="da00b-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="da00b-322">Set-csaccessedgeconfiguration</span><span class="sxs-lookup"><span data-stu-id="da00b-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="da00b-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="da00b-324">Set-csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="da00b-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="da00b-325">Set-cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="da00b-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="da00b-326">取得-CsQoEConfiguration 場合</span><span class="sxs-lookup"><span data-stu-id="da00b-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="da00b-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="da00b-328">Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="da00b-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="da00b-329">Set-csdialinconferencingconfiguration</span><span class="sxs-lookup"><span data-stu-id="da00b-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

