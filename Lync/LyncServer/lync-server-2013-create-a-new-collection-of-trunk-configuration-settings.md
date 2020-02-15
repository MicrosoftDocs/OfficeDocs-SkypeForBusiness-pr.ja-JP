---
title: 'Lync Server 2013: トランク構成設定の新しいコレクションの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04392b4157f0c1a12b0bcfa9e7125183a76864cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="433f7-102">Lync Server 2013 でのトランク構成設定の新しいコレクションの作成</span><span class="sxs-lookup"><span data-stu-id="433f7-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="433f7-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="433f7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="433f7-p101">SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="433f7-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="433f7-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="433f7-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="433f7-107">Real-time Transport Control Protocol (RTCP) パケットが送信される条件。</span><span class="sxs-lookup"><span data-stu-id="433f7-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="433f7-108">各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。</span><span class="sxs-lookup"><span data-stu-id="433f7-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="433f7-109">Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="433f7-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="433f7-110">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="433f7-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="433f7-111">Lync Server コントロールパネルを使用して SIP トランク構成設定を作成する場合、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="433f7-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="433f7-112">UI 設定</span><span class="sxs-lookup"><span data-stu-id="433f7-112">UI Setting</span></span></th>
<th><span data-ttu-id="433f7-113">PowerShell パラメーター</span><span class="sxs-lookup"><span data-stu-id="433f7-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="433f7-114">説明</span><span class="sxs-lookup"><span data-stu-id="433f7-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="433f7-115">名前</span><span class="sxs-lookup"><span data-stu-id="433f7-115">Name</span></span></p></td>
<td><p><span data-ttu-id="433f7-116">ID</span><span class="sxs-lookup"><span data-stu-id="433f7-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="433f7-p103">コレクションの一意の識別子。このプロパティは読み取り専用です。トランク構成設定のコレクションの Identity は変更できません。</span><span class="sxs-lookup"><span data-stu-id="433f7-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-119">説明</span><span class="sxs-lookup"><span data-stu-id="433f7-119">Description</span></span></p></td>
<td><p><span data-ttu-id="433f7-120">説明</span><span class="sxs-lookup"><span data-stu-id="433f7-120">Description</span></span></p></td>
<td><p><span data-ttu-id="433f7-121">管理者が、設定に関する追加情報を格納できます (たとえば、トランク構成の目的)。</span><span class="sxs-lookup"><span data-stu-id="433f7-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-122">サポートされる最大初期ダイアログの数</span><span class="sxs-lookup"><span data-stu-id="433f7-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="433f7-123">Maxんダイアログ</span><span class="sxs-lookup"><span data-stu-id="433f7-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="433f7-124">サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。</span><span class="sxs-lookup"><span data-stu-id="433f7-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-125">暗号化サポート レベル</span><span class="sxs-lookup"><span data-stu-id="433f7-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="433f7-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="433f7-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="433f7-127">仲介サーバーと、サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC 間のメディア トラフィックを保護するためのサポート レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="433f7-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="433f7-128">メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="433f7-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="433f7-129">メディア構成は、 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">get-csmediaconfiguration</a>コマンドレットおよび<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">get-csmediaconfiguration</a>コマンドレットを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="433f7-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="433f7-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="433f7-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="433f7-131">Required: SRTP 暗号化を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="433f7-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="433f7-132">Optional: ゲートウェイでサポートされている場合は、SRTP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="433f7-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="433f7-133">Not Supported: SRTP 暗号化がサポートされていないので、使用されません。</span><span class="sxs-lookup"><span data-stu-id="433f7-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="433f7-p105">SRTPMode は、ゲートウェイがトランスポート層セキュリティ (TLS) プロトコルを使用するよう構成されている場合にのみ使用されます。ゲートウェイがトランスポートとして伝送制御プロトコル (TCP) を使用するように構成されている場合は、SRTPMode は内部で Not Supported に設定されます。</span><span class="sxs-lookup"><span data-stu-id="433f7-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-136">サポートの参照</span><span class="sxs-lookup"><span data-stu-id="433f7-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="433f7-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="433f7-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="433f7-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="433f7-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="433f7-139">[<strong>ゲートウェイへの参照の送信を有効にする</strong>] に設定した場合、トランクが仲介サーバーからの REFER 要求の受信をサポートすることを示します。</span><span class="sxs-lookup"><span data-stu-id="433f7-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="433f7-140">[<strong>サードパーティ通話コントロールを使用する参照を有効にする</strong>] に設定すると、3PCC プロトコルを使用して転送される通話がホストされたサイトをバイパスできるようにすることを示します。</span><span class="sxs-lookup"><span data-stu-id="433f7-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="433f7-141">3pcc は、サードパーティ&quot;のコントロールとも&quot;呼ばれ、サードパーティが1組の呼び出し元を接続するために使用される場合 (たとえば、ユーザー a からユーザー B に電話をかけるオペレーターなど) に発生します。</span><span class="sxs-lookup"><span data-stu-id="433f7-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-142">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="433f7-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="433f7-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="433f7-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="433f7-p107">メディア バイパスがこのトランクに対して有効かどうかを示します。メディア バイパスは、[<strong>集中メディア処理</strong>] も有効になっている場合にのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="433f7-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-146">集中メディア処理</span><span class="sxs-lookup"><span data-stu-id="433f7-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="433f7-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="433f7-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="433f7-p108">既知のメディア終端ポイントがあるかどうかを示します (既知のメディア終端ポイントの例として、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイがあります)。</span><span class="sxs-lookup"><span data-stu-id="433f7-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-150">RTP ラッチを有効にする</span><span class="sxs-lookup"><span data-stu-id="433f7-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="433f7-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="433f7-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="433f7-p109">SIP トランクが RTP ラッチをサポートするかどうかを示します。RTP ラッチは、NAT (ネットワーク アドレス変換) 装置またはファイアウォールを経由した RTP/RTCP 接続を可能にする技術です。</span><span class="sxs-lookup"><span data-stu-id="433f7-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-154">着信転送履歴を有効にする</span><span class="sxs-lookup"><span data-stu-id="433f7-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="433f7-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="433f7-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="433f7-156">通話履歴の情報をトランク経由で転送するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="433f7-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-157">P-Asserted-Identity データの転送を有効にする</span><span class="sxs-lookup"><span data-stu-id="433f7-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="433f7-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="433f7-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="433f7-p110">P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。PAI ヘッダーがあれば、発信者 ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="433f7-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-161">送信ルーティング フェールオーバー タイマーを有効にする</span><span class="sxs-lookup"><span data-stu-id="433f7-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="433f7-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="433f7-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="433f7-p111">発信通話が 10 秒以内にゲートウェイによって応答されない場合に次に使用できるトランクにルーティングするかどうかを示します。他にトランクがない場合は、通話は自動的に破棄されます。ネットワークおよびゲートウェイの応答が遅い環境の場合、通話が不必要に破棄されるようになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="433f7-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-165">関連付けられている PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="433f7-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="433f7-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="433f7-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="433f7-167">トランクに割り当てられた PSTN 使用法のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="433f7-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-168">テストする変換後の番号</span><span class="sxs-lookup"><span data-stu-id="433f7-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="433f7-169">該当なし</span><span class="sxs-lookup"><span data-stu-id="433f7-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="433f7-170">トランクの構成設定の臨時テストを行うために使用できる電話番号です。</span><span class="sxs-lookup"><span data-stu-id="433f7-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-171">関連付けられている変換ルール</span><span class="sxs-lookup"><span data-stu-id="433f7-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="433f7-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="433f7-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="433f7-173">発信ルーティングによって処理される通話 (PBX または PSTN の宛先にルーティングされる通話) に適用される、電話番号変換ルールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="433f7-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-174">着信者番号の変換ルール</span><span class="sxs-lookup"><span data-stu-id="433f7-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="433f7-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="433f7-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="433f7-176">トランクに割り当てられた発信電話番号の変換ルールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="433f7-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-177">テストする電話番号</span><span class="sxs-lookup"><span data-stu-id="433f7-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="433f7-178">該当なし</span><span class="sxs-lookup"><span data-stu-id="433f7-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="433f7-179">変換ルールの臨時テストを行うために使用できる電話番号です。</span><span class="sxs-lookup"><span data-stu-id="433f7-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="433f7-180">発信者番号</span><span class="sxs-lookup"><span data-stu-id="433f7-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="433f7-181">該当なし</span><span class="sxs-lookup"><span data-stu-id="433f7-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="433f7-182">テストする電話番号が発信者の電話番号であることを示します。</span><span class="sxs-lookup"><span data-stu-id="433f7-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="433f7-183">着信者番号</span><span class="sxs-lookup"><span data-stu-id="433f7-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="433f7-184">該当なし</span><span class="sxs-lookup"><span data-stu-id="433f7-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="433f7-185">テストする電話番号が着信者の電話番号であることを示します。</span><span class="sxs-lookup"><span data-stu-id="433f7-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="433f7-186">Lync Server Get-cstrunkconfiguration コマンドレットでは、Lync Server コントロールパネルに表示されない追加のプロパティをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="433f7-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="433f7-187">詳細については、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">get-cstrunkconfiguration</A>コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="433f7-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="433f7-188">Lync Server コントロールパネルを使用して新しいトランク構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="433f7-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="433f7-189">Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="433f7-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="433f7-190">[**トランク構成**] タブで [**新規作成**] をクリックします。新しい設定をサイト スコープで作成する場合は [**サイト トランク**]  をクリックし、サービス スコープで作成する場合は [**プール トランク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="433f7-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="433f7-p113">[**サイトの選択**] または [**サービスの選択**] ダイアログ ボックスで (表示されるダイアログ ボックスは、サイト スコープとサービス スコープのどちらの設定を作成するかによって異なります)、新しい構成設定の場所を選択し、[**OK**] をクリックします。ダイアログ ボックスが空白の場合は、新しい設定を作成する場所がないことを意味します。たとえば、[**サイトの選択**] ダイアログ ボックスが空白の場合、すべてのサイトにトランク構成サイトのコレクションが既に割り当てられており、各サイト (および各サービス) でホストできるのは該当のコレクションだけであることを示しています。この場合、既存のコレクションを削除して新しいコレクションを作成することも、既存のコレクションを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="433f7-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="433f7-194">[**新規トランク構成**] ダイアログで、適切な選択を行って [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="433f7-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="433f7-p114">コレクションの [**状態**] プロパティが [**コミットされていません**] に更新されます。変更をコミットし、コレクションを削除するには、[**コミット**]、[**すべてコミット**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="433f7-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="433f7-197">[**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="433f7-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="433f7-198">[**Microsoft Lync Server 2013 Control Panel**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="433f7-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

