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
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="3387a-102">Lync Server 2013 でフォレストのグローバル設定の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="3387a-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3387a-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="3387a-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="3387a-104">管理者は、Lync Server 2013 展開のグローバル設定を毎月確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="3387a-105">目標として、実装されている設定を既知の構成のセットと照らし合わせて確認します。設定は有効であることを保証し、ベースラインのドキュメントを更新する必要があるかどうかを判断するための基準構成となります。</span><span class="sxs-lookup"><span data-stu-id="3387a-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="3387a-106">グローバル設定の変更は、新しい設定の文書化を含める必要がある変更管理プロセスによって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="3387a-107">レビューする必要があるグローバル設定については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="3387a-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="3387a-108">全般設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-108">Check general settings</span></span>

<span data-ttu-id="3387a-109">Lync Server 2013 でサポートされているセッション開始プロトコル (SIP) ドメインなど、一般的な設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="3387a-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="3387a-110">SIP ドメイン情報は、Windows PowerShell と**CsSipDomain**コマンドレットを使って返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3387a-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="3387a-111">この情報を返すには、 `Get-CsSipDomain` Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3387a-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="3387a-112">CsSipDomain は、認証されたすべての SIP ドメインについて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="3387a-113">識別名の IsDefault</span><span class="sxs-lookup"><span data-stu-id="3387a-113">Identity Name IsDefault</span></span>

<span data-ttu-id="3387a-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="3387a-114">\-------- ---- ---------</span></span>

<span data-ttu-id="3387a-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="3387a-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="3387a-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="3387a-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="3387a-117">IsDefault プロパティが True に設定されている場合、対応するドメインは既定の SIP ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="3387a-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="3387a-118">CsSipDomain コマンドレットを使用して、組織の既定の SIP ドメインを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="3387a-119">ただし、既定のドメインがないままであるため、既定の SIP ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3387a-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="3387a-120">(前の例で示したように) fabrikam.com ドメインを削除する場合は、最初に既定のドメインとなるように na.fabrikam.com を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="3387a-121">会議の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-121">Check meeting settings</span></span>

<span data-ttu-id="3387a-122">会議の設定には、会議のポリシー定義と、会議での匿名ユーザーの参加のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3387a-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="3387a-123">会議の構成設定を取得するには、Windows PowerShell を使用するか、または**csmeeting 構成**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="3387a-124">たとえば、次のコマンドは、グローバル会議の構成設定に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="3387a-125">Cs会議構成– Id "グローバル" 会議の構成設定は、サイトのスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="3387a-126">そのため、次のコマンドを使用することができます。これは、すべての会議の構成設定に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="3387a-127">**Cs会議構成**コマンドレットは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="3387a-128">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-128">Identity : Global</span></span>

<span data-ttu-id="3387a-129">PstnCallersBypassLobby: True</span><span class="sxs-lookup"><span data-stu-id="3387a-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="3387a-130">EnableAssignedConferenceType: True</span><span class="sxs-lookup"><span data-stu-id="3387a-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="3387a-131">デザインの発表者: 会社</span><span class="sxs-lookup"><span data-stu-id="3387a-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="3387a-132">AssignedConferenceTypeByDefault: True</span><span class="sxs-lookup"><span data-stu-id="3387a-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="3387a-133">AdmitAnonymousUsersByDefault: True</span><span class="sxs-lookup"><span data-stu-id="3387a-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="3387a-134">**AdmitAnonymousUsersByDefault**の最後の項目では、匿名ユーザーが会議に参加する機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="3387a-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="3387a-135">会議の構成設定を確認するときに、現在の設定を既定の対応する値と比較すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="3387a-136">次のコマンドを実行して、既定の会議構成設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3387a-137">前のコマンドでは、グローバル会議構成設定のメモリ内のインスタンス (各プロパティの既定値を使用するインスタンス) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="3387a-138">このコマンドを実行しても、実際の会議の構成設定は作成されません。</span><span class="sxs-lookup"><span data-stu-id="3387a-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="3387a-139">ただし、すべての既定のプロパティ値が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="3387a-140">エッジサーバーとその設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="3387a-141">エッジサーバーの情報は、Windows PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="3387a-142">このコマンドは、組織で使用するように構成されているすべてのエッジサーバーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="3387a-143">返される情報には、各エッジサーバーの FQDN とポートの設定がすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="3387a-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="3387a-144">Id: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3387a-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="3387a-145">レジストラー: レジストラー: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3387a-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="3387a-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="3387a-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="3387a-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="3387a-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="3387a-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="3387a-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="3387a-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="3387a-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="3387a-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="3387a-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="3387a-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="3387a-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="3387a-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="3387a-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="3387a-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="3387a-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="3387a-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="3387a-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="3387a-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="3387a-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="3387a-156">MediaCommunicationPortStart: 5万</span><span class="sxs-lookup"><span data-stu-id="3387a-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="3387a-157">MediaComunicationPortCount: 1万</span><span class="sxs-lookup"><span data-stu-id="3387a-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="3387a-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3387a-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3387a-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3387a-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3387a-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="3387a-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="3387a-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="3387a-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="3387a-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3387a-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3387a-163">DependentServiceList: {レジストラー: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="3387a-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="3387a-164">ConferencingServer: LYNC-SE</span><span class="sxs-lookup"><span data-stu-id="3387a-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="3387a-165">com、MediationServer: LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="3387a-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="3387a-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="3387a-166">fabrikam.com}</span></span>

<span data-ttu-id="3387a-167">ServiceId: fabrikam.com-EdgeServer</span><span class="sxs-lookup"><span data-stu-id="3387a-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="3387a-168">SiteId: サイト: fabrikam</span><span class="sxs-lookup"><span data-stu-id="3387a-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="3387a-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3387a-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3387a-170">バージョン: 5</span><span class="sxs-lookup"><span data-stu-id="3387a-170">Version : 5</span></span>

<span data-ttu-id="3387a-171">役割: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="3387a-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="3387a-172">フェデレーション設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-172">Check federation settings</span></span>

<span data-ttu-id="3387a-173">構成されているかどうかなど、フェデレーション設定を確認します。回答が "yes" の場合は、FQDN とポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="3387a-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="3387a-174">フェデレーションは、アクセスエッジ構成のグローバルコレクションを使って有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="3387a-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="3387a-175">特に、フェデレーションがすべてまたはまったく機能していないことを意味します。組織全体でフェデレーションが有効になっているか、組織全体でフェデレーションが無効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3387a-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="3387a-176">アクセスエッジの構成設定は、Windows PowerShell を使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3387a-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="3387a-177">そのためには、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3387a-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="3387a-178">このコマンドを実行すると、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="3387a-179">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-179">Identity : Global</span></span>

<span data-ttu-id="3387a-180">AllowAnonymousUsers: False</span><span class="sxs-lookup"><span data-stu-id="3387a-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="3387a-181">AllowFederatedUsers: False</span><span class="sxs-lookup"><span data-stu-id="3387a-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="3387a-182">AllowOutsideUsers: False</span><span class="sxs-lookup"><span data-stu-id="3387a-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="3387a-183">BeClearingHouse: False</span><span class="sxs-lookup"><span data-stu-id="3387a-183">BeClearingHouse : False</span></span>

<span data-ttu-id="3387a-184">EnablePartnerDiscovery: False</span><span class="sxs-lookup"><span data-stu-id="3387a-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="3387a-185">EnableArchivingDisclaimer: False</span><span class="sxs-lookup"><span data-stu-id="3387a-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="3387a-186">KeepCrlsUpToDateForPeers: True</span><span class="sxs-lookup"><span data-stu-id="3387a-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="3387a-187">MarkSourceVerifiableOnOutgoingMessages: True</span><span class="sxs-lookup"><span data-stu-id="3387a-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="3387a-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="3387a-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="3387a-189">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="3387a-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="3387a-190">**AllowFederatedUsers**プロパティが True に設定されている場合は、組織でフェデレーションが有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3387a-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="3387a-191">( **AllowFederatedUsers**を True に設定すると、分割されたドメインのシナリオでは、オンプレミスのユーザーはクラウド内のユーザーとシームレスに通信できることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="3387a-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="3387a-192">エッジサーバーの FQDN とポートの設定を取得するには、前のタスク (エッジサーバーとその設定) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3387a-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="3387a-193">グローバルスコープでフェデレーションを有効にすると、ユーザーはフェデレーションされたユーザーと通信できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="3387a-194">個々のユーザーが実際にフェデレーションユーザーと通信できるかどうかを判断するには、そのユーザーに割り当てられている外部ユーザーアクセスポリシーを調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="3387a-195">外部ユーザーアクセスの情報は、Windows PowerShell を使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3387a-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="3387a-196">たとえば、次のコマンドは、グローバル外部ユーザーアクセスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="3387a-197">このコマンドは、すべての外部ユーザーアクセスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="3387a-198">返される情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3387a-198">The returned information will resemble this:</span></span>

<span data-ttu-id="3387a-199">Id: False</span><span class="sxs-lookup"><span data-stu-id="3387a-199">Identity : False</span></span>

<span data-ttu-id="3387a-200">説明</span><span class="sxs-lookup"><span data-stu-id="3387a-200">Description :</span></span>

<span data-ttu-id="3387a-201">EnableFederationAccess: False</span><span class="sxs-lookup"><span data-stu-id="3387a-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="3387a-202">EnablePublicCloudAccess: False</span><span class="sxs-lookup"><span data-stu-id="3387a-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="3387a-203">EnablePublicCloudAccessAudioVideoAccess: False</span><span class="sxs-lookup"><span data-stu-id="3387a-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="3387a-204">EnableOutsideAccess: False</span><span class="sxs-lookup"><span data-stu-id="3387a-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="3387a-205">**EnableFederationAccess**が True に設定されている場合、特定のポリシーによって管理されるユーザーはフェデレーションユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="3387a-206">アーカイブ設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-206">Check archiving settings</span></span>

<span data-ttu-id="3387a-207">内部およびフェデレーションされた通信のアーカイブ設定を確認します。内部および外部のアーカイブの設定を確認する前に、アーカイブが有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3387a-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="3387a-208">アーカイブ構成の設定を確認するには、Windows PowerShell と CsArchivingConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="3387a-209">アーカイブ設定は、サイトのスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="3387a-210">すべてのアーカイブ設定に関する情報を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="3387a-211">CsArchivingConfiguration コマンドレットを実行すると、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="3387a-212">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-212">Identity : Global</span></span>

<span data-ttu-id="3387a-213">EnableArchiving: False</span><span class="sxs-lookup"><span data-stu-id="3387a-213">EnableArchiving : False</span></span>

<span data-ttu-id="3387a-214">EnablePurging: False</span><span class="sxs-lookup"><span data-stu-id="3387a-214">EnablePurging : False</span></span>

<span data-ttu-id="3387a-215">PurgeExportedArchivesOnly: False</span><span class="sxs-lookup"><span data-stu-id="3387a-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="3387a-216">Blockonアーカイブエラー: False</span><span class="sxs-lookup"><span data-stu-id="3387a-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="3387a-217">KeepArchivingDataForDays:14</span><span class="sxs-lookup"><span data-stu-id="3387a-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="3387a-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="3387a-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="3387a-219">ArchiveDuplicateMessages: True</span><span class="sxs-lookup"><span data-stu-id="3387a-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="3387a-220">CachePurgingInterval:24</span><span class="sxs-lookup"><span data-stu-id="3387a-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="3387a-221">EnableArchiving プロパティが False に設定されている場合は、通信セッションがアーカイブされないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3387a-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="3387a-222">インスタントメッセージングセッションのみをアーカイブする場合は、次のようなコマンドを使用して、IM セッションのアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3387a-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="3387a-223">会議セッションとインスタントメッセージングセッションをアーカイブするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="3387a-224">現在のアーカイブ設定と既定の設定を比較する場合は、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3387a-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3387a-225">このコマンドによって、グローバルアーカイブ構成の設定のメモリ内のみのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="3387a-226">これは、Lync Server によって使用される設定の実際のコレクションではありません。</span><span class="sxs-lookup"><span data-stu-id="3387a-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="3387a-227">ただし、すべてのアーカイブ構成プロパティの既定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="3387a-228">このコマンドを使用して、アーカイブサーバーの FQDN を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="3387a-229">アーカイブが有効になっていることを確認したら、アーカイブポリシーを表示して、内部と外部の通信セッションがアーカイブされているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="3387a-230">CsArchivingPolicy コマンドレットを使用して、アーカイブポリシー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="3387a-231">たとえば、次のコマンドはグローバルアーカイブポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="3387a-232">アーカイブポリシーは、サイトとユーザーごとのスコープで構成することもできるため、次のコマンドを使用して、すべてのアーカイブポリシーに関する情報を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="3387a-233">CsArchivingPolicy から受け取った情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3387a-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="3387a-234">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-234">Identity : Global</span></span>

<span data-ttu-id="3387a-235">説明</span><span class="sxs-lookup"><span data-stu-id="3387a-235">Description :</span></span>

<span data-ttu-id="3387a-236">アーカイブ内部: False</span><span class="sxs-lookup"><span data-stu-id="3387a-236">ArchiveInternal : False</span></span>

<span data-ttu-id="3387a-237">アーカイブ外部: False</span><span class="sxs-lookup"><span data-stu-id="3387a-237">ArchiveExternal : False</span></span>

<span data-ttu-id="3387a-238">アーカイブポリシーでは、既定では、内部および外部のアーカイブの両方が無効になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3387a-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="3387a-239">CDR の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-239">Check CDR settings</span></span>

<span data-ttu-id="3387a-240">ピアツーピア、電話会議、音声通話の詳細記録の通話の詳細レコード (CDR) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="3387a-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="3387a-241">CDR の設定の詳細については、CsCdrConfiguration コマンドレットを使用して**取得**できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="3387a-242">たとえば、次のコマンドは、CDR 構成設定のグローバルコレクションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="3387a-243">また、CDR はサイトのスコープでも設定できるため、このコマンドを実行することもできます。これは、すべての CDR 構成の設定に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="3387a-244">CsCdrConfiguration コマンドレットは、CDR 構成設定のコレクションごとに、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="3387a-245">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-245">Identity : Global</span></span>

<span data-ttu-id="3387a-246">EnableCDR: True</span><span class="sxs-lookup"><span data-stu-id="3387a-246">EnableCDR : True</span></span>

<span data-ttu-id="3387a-247">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="3387a-247">EnablePurging : True</span></span>

<span data-ttu-id="3387a-248">KeepCallDetailForDays:60</span><span class="sxs-lookup"><span data-stu-id="3387a-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="3387a-249">KeepErrorReportForDays:60</span><span class="sxs-lookup"><span data-stu-id="3387a-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="3387a-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="3387a-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="3387a-251">QoE の監視についても同様の情報を取得するには、CsQoEConfiguration 指定コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="3387a-252">たとえば、次のコマンドは、QoE 構成設定のグローバルコレクションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="3387a-253">この情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3387a-253">That information will resemble this:</span></span>

<span data-ttu-id="3387a-254">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-254">Identity : Global</span></span>

<span data-ttu-id="3387a-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="3387a-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="3387a-256">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="3387a-256">EnablePurging : True</span></span>

<span data-ttu-id="3387a-257">KeepQoEDataForDays:60</span><span class="sxs-lookup"><span data-stu-id="3387a-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="3387a-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="3387a-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="3387a-259">EnableExternalConsumer: False</span><span class="sxs-lookup"><span data-stu-id="3387a-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="3387a-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="3387a-260">ExternalConsumerName :</span></span>

<span data-ttu-id="3387a-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="3387a-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="3387a-262">EnableQoE: True</span><span class="sxs-lookup"><span data-stu-id="3387a-262">EnableQoE : True</span></span>

<span data-ttu-id="3387a-263">現在の CDR 設定と既定の CDR 設定を比較する場合は、次のコマンドを実行して既定値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3387a-264">同様に、次のコマンドを使用して、QoE モニターの既定値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3387a-265">このコマンドを実行して、監視サーバーの FQDN を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="3387a-266">音声の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-266">Check voice settings</span></span>

<span data-ttu-id="3387a-267">音声の設定は、通常、管理者にとって重要です。音声ポリシーには、個々のユーザーに対して公開される機能を決定する設定 (通話の転送や転送機能など) が含まれます。ボイスルートは、通話が PSTN を介してどのようにルーティングされるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3387a-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="3387a-268">音声ポリシー情報は、Windows PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="3387a-269">たとえば、次のコマンドはグローバルボイスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="3387a-270">このコマンドは、組織で使用するように構成されているすべてのボイスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="3387a-271">CsVoicePolicy コマンドレットによって返される情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3387a-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="3387a-272">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-272">Identity : Global</span></span>

<span data-ttu-id="3387a-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="3387a-273">PstnUsages : {}</span></span>

<span data-ttu-id="3387a-274">説明</span><span class="sxs-lookup"><span data-stu-id="3387a-274">Description :</span></span>

<span data-ttu-id="3387a-275">AllowSimulRing: True</span><span class="sxs-lookup"><span data-stu-id="3387a-275">AllowSimulRing : True</span></span>

<span data-ttu-id="3387a-276">AllowCallForwarding: True</span><span class="sxs-lookup"><span data-stu-id="3387a-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="3387a-277">AllowPSTNReRouting: True</span><span class="sxs-lookup"><span data-stu-id="3387a-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="3387a-278">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="3387a-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="3387a-279">EnableDelegation: True</span><span class="sxs-lookup"><span data-stu-id="3387a-279">EnableDelegation : True</span></span>

<span data-ttu-id="3387a-280">EnableTeamCall: True</span><span class="sxs-lookup"><span data-stu-id="3387a-280">EnableTeamCall : True</span></span>

<span data-ttu-id="3387a-281">EnableCallTransfer: True</span><span class="sxs-lookup"><span data-stu-id="3387a-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="3387a-282">EnableCallPark: False</span><span class="sxs-lookup"><span data-stu-id="3387a-282">EnableCallPark : False</span></span>

<span data-ttu-id="3387a-283">EnableMaliciousCallTracing: False</span><span class="sxs-lookup"><span data-stu-id="3387a-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="3387a-284">EnableBWPolicyOverride: False</span><span class="sxs-lookup"><span data-stu-id="3387a-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="3387a-285">PreventPSTNTollBypass: False</span><span class="sxs-lookup"><span data-stu-id="3387a-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="3387a-286">音声ポリシーのサブセットを返すクエリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="3387a-287">たとえば、次のコマンドは、着信の転送を許可するすべての音声ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="3387a-288">このコマンドは、着信の転送を許可していないすべての音声ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="3387a-289">Windows PowerShell では、CsVoiceRouting コマンドレットを使用して、音声ルートに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3387a-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="3387a-290">このコマンドは、すべての音声ルートについて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="3387a-291">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="3387a-291">Identity : LocalRoute</span></span>

<span data-ttu-id="3387a-292">優先度: 0</span><span class="sxs-lookup"><span data-stu-id="3387a-292">Priority : 0</span></span>

<span data-ttu-id="3387a-293">説明</span><span class="sxs-lookup"><span data-stu-id="3387a-293">Description :</span></span>

<span data-ttu-id="3387a-294">数字パターン: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="3387a-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="3387a-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="3387a-295">PstnUsages : {}</span></span>

<span data-ttu-id="3387a-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="3387a-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="3387a-297">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="3387a-297">Name : LocalRoute</span></span>

<span data-ttu-id="3387a-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="3387a-298">SuppressCallerId :</span></span>

<span data-ttu-id="3387a-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="3387a-299">AlternateCallerId :</span></span>

<span data-ttu-id="3387a-300">Lync Server を使用すると、PSTN を使わず、PSTN ゲートウェイを指定しないボイスルートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3387a-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="3387a-301">ただし、この2つのプロパティ値が構成されていないボイスルーティングでは、実際に着信をルーティングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3387a-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="3387a-302">そのため、このコマンドを定期的に実行すると便利な場合があります。これは、PSTN を使用していないボイスルートの id を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="3387a-303">同様に、このコマンドは、PSTN ゲートウェイを使用するように構成されていないすべてのボイスルートの id を返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="3387a-304">会議アテンダントの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3387a-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="3387a-305">PSTN ダイヤルイン会議の会議アテンダントの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="3387a-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="3387a-306">会議アテンダントの設定を取得するには、 **CsDialInConferencingConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="3387a-307">これらの設定は Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3387a-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="3387a-308">会議アテンダントの設定を表示するには、次のような Windows PowerShell コマンドを使います。これは、会議アテンダント設定のグローバルコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="3387a-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="3387a-309">会議アテンダントの設定は、サイトのスコープで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3387a-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="3387a-310">会議アテンダントのすべての設定に関する情報を取得するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3387a-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="3387a-311">CsDialInConferencingConfiguration コマンドレットを実行すると、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="3387a-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="3387a-312">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="3387a-312">Identity : Global</span></span>

<span data-ttu-id="3387a-313">Entryexitアナウンスの場合: UseNames</span><span class="sxs-lookup"><span data-stu-id="3387a-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="3387a-314">EnableNameRecording: True</span><span class="sxs-lookup"><span data-stu-id="3387a-314">EnableNameRecording : True</span></span>

<span data-ttu-id="3387a-315">EntryExitAnnouncementsEnabledByDefault: False</span><span class="sxs-lookup"><span data-stu-id="3387a-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="3387a-316">EntryExitAnnouncementsEnabledByDefault が False に設定されている場合は、会議のアナウンスが無効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3387a-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="3387a-317">エントリと終了のアナウンスを有効にするには、次のように Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3387a-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3387a-318">関連項目</span><span class="sxs-lookup"><span data-stu-id="3387a-318">See Also</span></span>


[<span data-ttu-id="3387a-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="3387a-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="3387a-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3387a-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="3387a-321">CsService の入手</span><span class="sxs-lookup"><span data-stu-id="3387a-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="3387a-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="3387a-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="3387a-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3387a-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="3387a-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3387a-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="3387a-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="3387a-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="3387a-326">取得-CsQoEConfiguration しくみ</span><span class="sxs-lookup"><span data-stu-id="3387a-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="3387a-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="3387a-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="3387a-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="3387a-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="3387a-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3387a-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

