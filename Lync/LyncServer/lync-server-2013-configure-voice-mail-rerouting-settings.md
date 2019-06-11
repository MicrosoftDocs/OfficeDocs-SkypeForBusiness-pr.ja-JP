---
title: 'Lync Server 2013: ボイス メール再ルーティング設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="9b19f-102">Lync Server 2013 でのボイス メール再ルーティング設定の構成</span><span class="sxs-lookup"><span data-stu-id="9b19f-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b19f-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9b19f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9b19f-104">Exchange ユニファイドメッセージング (UM) がセントラルサイトにインストールされていて、Exchange UM メッセージ自動応答 (AA) が展開されている場合は、Survivable Branch アプライアンスと Survivable ブランチサーバーで、WAN の停止中に、支店のユーザーに対してボイスメール survivability を提供できます。</span><span class="sxs-lookup"><span data-stu-id="9b19f-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="9b19f-105">Exchange 管理者がメッセージのみを受け取るように AA を構成することをお勧めします。これは、ユーザーへの転送や、オペレーターへの転送などの一般的な機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b19f-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="9b19f-106">または、一般的な AA またはカスタマイズした AA を使って通話をルーティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9b19f-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="9b19f-107">詳細については、計画ドキュメントの「 [Lync Server 2013 のブランチサイトの回復要件](lync-server-2013-branch-site-resiliency-requirements.md)」セクションの「ボイスメールの Survivability の準備」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b19f-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="9b19f-108">ボイスメールの survivability を構成するには</span><span class="sxs-lookup"><span data-stu-id="9b19f-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="9b19f-109">Exchange 管理者に、メッセージのみを受け取るように AA を構成するように依頼します (Exchange Shell では、次のコマンドレットを使用します。 **Set-UMAutoAttendant \<AA 名\> -calla oneenabled $false**。</span><span class="sxs-lookup"><span data-stu-id="9b19f-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="9b19f-110">メッセージを残すことを許可するように指定するパラメーター (*SendVoiceMsgEnabled*) は、既定では true です。</span><span class="sxs-lookup"><span data-stu-id="9b19f-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="9b19f-111">Lync Server 管理シェルで、 **CSVoiceMailReroutingConfiguration**コマンドレットを使用して、Survivable Branch アプライアンスのボイスメール再ルーティング構成の Exchange UM 自動応答の電話番号として AA 電話番号を設定します。Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="9b19f-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b19f-112">後でボイスメールの再ルーティング設定を変更する必要がある場合は、 <STRONG>CsVoiceMailReRoutingConfiguration</STRONG>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b19f-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="9b19f-113">詳細について<STRONG></STRONG>は、Shell のヘルプトピックを参照してください。 <STRONG>CSVoiceMailReroutingConfiguration</STRONG>の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b19f-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="9b19f-114">ブランチユーザーの Exchange UM ダイヤルプランに対応する Exchange um サブスクライバーアクセス番号を、Survivable Branch Appliance または Survivable ブランチサーバーのボイスメール再ルーティング構成の Exchange UM サブスクライバーアクセス番号として設定します。</span><span class="sxs-lookup"><span data-stu-id="9b19f-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b19f-115">WAN の停止中にボイスメール機能にアクセスする必要があるすべての支店ユーザーに関連付けられたダイヤルプランが1つだけになるように、Exchange UM ユーザーのダイヤルプランを構成します。</span><span class="sxs-lookup"><span data-stu-id="9b19f-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="9b19f-116">Survivable Branch Appliance または Survivable ブランチサーバーの**次の手順**: [Lync Server 2013 で Survivable ブランチアプライアンスまたはサーバーのホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9b19f-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

