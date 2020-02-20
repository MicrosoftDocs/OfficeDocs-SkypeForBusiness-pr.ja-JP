---
title: 'Lync Server 2013: ボイスメール再ルーティング設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38818a6514d4d7bce5266df57347415a600a28c8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="51388-102">Lync Server 2013 でボイスメールの再ルーティング設定を構成する</span><span class="sxs-lookup"><span data-stu-id="51388-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51388-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="51388-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="51388-104">存続可能 Branch アプライアンスおよび存続可能ブランチサーバーは、Exchange ユニファイドメッセージング (UM) が中央サイトにインストールされていて、Exchange UM メッセージ自動応答 (AA) が展開されている場合、WAN の停止時にブランチユーザーにボイスメール存続性を提供できます。</span><span class="sxs-lookup"><span data-stu-id="51388-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="51388-105">Exchange 管理者は、メッセージのみを受け入れるように AA を構成することをお勧めします。これは、ユーザーへの転送、またはオペレーターへの転送など、他の一般的な機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="51388-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="51388-106">または、通話をルーティングするために汎用 AA または AA をカスタマイズして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="51388-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="51388-107">詳細については、「計画」のドキュメントの「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」セクションの「ボイスメールの存続性の準備」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51388-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="51388-108">ボイス メールの存続性を構成するには</span><span class="sxs-lookup"><span data-stu-id="51388-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="51388-109">Exchange 管理者に、メッセージのみを受け入れるように AA を構成するように依頼します (Exchange シェルでは、次のコマンドレットを使用します。 **Set \<-umautoattendant AA 名\> -calla oneenabled $false**。</span><span class="sxs-lookup"><span data-stu-id="51388-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="51388-110">メッセージを残すことを許可するかどうかを指定するパラメーター (*SendVoiceMsgEnabled*) は、既定では true になっています。</span><span class="sxs-lookup"><span data-stu-id="51388-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="51388-111">Lync Server 管理シェルで、 **get-csvoicemailreroutingconfiguration**コマンドレットを使用して、存続可能 branch Appliance または存続可能ブランチサーバーのボイスメール再ルーティング構成で、Exchange UM 自動応答の電話番号として AA 電話番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="51388-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="51388-112">ボイス メール再ルーティング設定を後で変更する必要がある場合は、<STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> コマンドレットを使用して変更します。</span><span class="sxs-lookup"><span data-stu-id="51388-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="51388-113"><STRONG>New-</STRONG> および <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> の詳細については、シェル ヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51388-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="51388-114">ブランチユーザーの Exchange UM ダイヤルプランに対応する Exchange UM サブスクライバーアクセス番号を、存続可能 Branch Appliance または存続可能ブランチサーバーのボイスメール再ルーティング構成の Exchange um サブスクライバーアクセス番号として設定します。</span><span class="sxs-lookup"><span data-stu-id="51388-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="51388-115">WAN の停止時にボイスメール機能にアクセスする必要があるすべてのブランチユーザーに関連付けられたダイヤルプランが1つだけになるように、Exchange UM ユーザーのダイヤルプランを構成します。</span><span class="sxs-lookup"><span data-stu-id="51388-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="51388-116">存続可能 Branch Appliance または存続可能ブランチサーバーの**次のステップ**: [Lync Server 2013 の存続可能ブランチアプライアンスまたはサーバーのホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="51388-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

