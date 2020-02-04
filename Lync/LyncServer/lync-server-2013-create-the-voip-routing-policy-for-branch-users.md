---
title: 'Lync Server 2013: ブランチ ユーザー用の VoIP ルーティング ポリシーの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="066db-102">Lync Server 2013 でのブランチ ユーザー用の VoIP ルーティング ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="066db-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="066db-103">_**最終更新日:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="066db-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="066db-104">ブランチサイトのユーザーに対して、個別のボイスオーバー IP (VoIP) ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="066db-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="066db-105">このポリシーには、Survivable Branch Appliance ゲートウェイまたは Survivable ブランチサーバーの外部ゲートウェイからの出口へのルート、および中央サイトのゲートウェイからの出口へのバックアップルートを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="066db-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="066db-106">ユーザーが登録されている場所に関係なく、Survivable Branch Appliance または Survivable Branch Server のレジストラー、またはセントラルサイトのバックアップレジストラークラスターでは、ユーザーの VoIP ポリシーが常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="066db-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="066db-107">ブランチユーザーの VoIP ルーティングポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="066db-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="066db-108">ユーザーレベルのダイヤルプランを作成して、ブランチユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="066db-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="066db-109">(操作のドキュメントにある「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="066db-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="066db-110">そのサイトのユーザーのダイヤルの傾向に対応する正規化ルールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="066db-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="066db-111">Survivable Branch Appliance または Survivable Branch Server ユーザーがセントラルサイトのバックアップレジストラープールにフェールオーバーした場合、同じダイヤルプランが有効になります。</span><span class="sxs-lookup"><span data-stu-id="066db-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="066db-112">(操作のドキュメントにある「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="066db-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="066db-113">Survivable Branch Appliance ゲートウェイまたは Survivable ブランチサーバー外部ゲートウェイから egresses されるボイスルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="066db-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="066db-114">(操作のドキュメントの「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="066db-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="066db-115">Survivable Branch Appliance または Survivable Branch Server ゲートウェイでバックアップのレジストラープール (仲介サーバーに接続されている) をセントラルサイトで参照するように設定します。</span><span class="sxs-lookup"><span data-stu-id="066db-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="066db-116">(Survivable Branch Appliance または Survivable Branch Server ベンダーのマニュアルを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="066db-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="066db-117">このバックアップ通話ルーティングのセットアップは、Survivable Branch Appliance または Survivable Branch Server が利用できない場合 (たとえば、メンテナンスのために停止している場合など) に、ブランチユーザーへの着信通話が機能するようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="066db-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="066db-118">Survivable Branch Appliance または Survivable ブランチサーバー上のレジストラーと仲介サーバーが使用できず、ユーザーがセントラルサイトのバックアップレジストラープールに登録されている場合は、着信通話をユーザーにルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="066db-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="066db-119">**次の手順**: [Lync Server 2013 でボイスメールの再ルーティング設定を構成する](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="066db-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

