---
title: 'Lync Server 2013: トランク構成情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77f53a4263fd0e0b64ccd6894d27e30c0c5be95c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="ffc9c-102">Lync Server 2013 でのトランク構成情報の表示</span><span class="sxs-lookup"><span data-stu-id="ffc9c-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc9c-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ffc9c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ffc9c-104">SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="ffc9c-105">たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="ffc9c-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="ffc9c-107">リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="ffc9c-108">各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="ffc9c-109">Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="ffc9c-110">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="ffc9c-111">Lync Server コントロールパネルを使用して SIP トランクの構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="ffc9c-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ffc9c-112">Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="ffc9c-113">[**トランクの構成**] タブに、すべてのトランク構成設定のコレクションの一覧が表示されます。各コレクションについて、**名前**、**スコープ**、**状態**、**メディアバイパス**の各プロパティの値と共に、 **PSTN 使用**量、**通話番号の規則**、コレクションに関連付けられている**番号ルール**の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="ffc9c-114">トランク構成設定のコレクションに関する追加情報を表示するには、目的のコレクションをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="ffc9c-115">一度に1つのトランク構成設定のコレクションについてのみ、詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ffc9c-116">Windows PowerShell コマンドレットを使用した SIP トランク構成情報の表示</span><span class="sxs-lookup"><span data-stu-id="ffc9c-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ffc9c-117">SIP トランク構成設定は、Lync Server PowerShell と Set-cstrunkconfiguration コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="ffc9c-118">このコマンドレットは、Lync Server 2013 Management Shell またはリモートセッション Windows PowerShell から実行できます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="ffc9c-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="ffc9c-120">SIP トランクの構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="ffc9c-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="ffc9c-121">SIP トランク構成のすべての設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="ffc9c-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-122">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

<span data-ttu-id="ffc9c-123">詳細については、 [set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffc9c-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

