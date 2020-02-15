---
title: 'Lync Server 2013: ブランチユーザーの VoIP ルーティングポリシーの作成'
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
ms.openlocfilehash: 308c4ad3a7371c9a27f668b79623a512227623b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="20824-102">Lync Server 2013 でのブランチユーザーの VoIP ルーティングポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="20824-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20824-103">_**トピックの最終更新日:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="20824-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="20824-104">ブランチ サイトのユーザーを対象に独立したボイス オーバー IP (VoIP) ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20824-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="20824-105">このポリシーには、存続可能 Branch Appliance gateway または存続可能ブランチサーバーの外部ゲートウェイから出口へのルートと、中央サイトのゲートウェイから出力されるバックアップルートを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="20824-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="20824-106">ユーザーが登録されている場所に関係なく、存続可能 Branch Appliance または存続可能 Branch Server または中央サイトのバックアップレジストラークラスターのレジストラーでは、ユーザーの VoIP ポリシーが常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="20824-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="20824-107">ブランチ ユーザーの VoIP ルーティング ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="20824-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="20824-108">ユーザーレベルのダイヤルプランを作成して、ブランチユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20824-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="20824-109">(「操作」のドキュメントの「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="20824-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="20824-110">そのサイトのユーザーのダイヤル傾向に対応する正規化ルールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20824-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="20824-111">存続可能 Branch Appliance または存続可能 Branch Server ユーザーがセントラルサイトのバックアップレジストラープールにフェールオーバーすると、同じダイヤルプランが有効になります。</span><span class="sxs-lookup"><span data-stu-id="20824-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="20824-112">(「操作」のドキュメントの「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="20824-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="20824-113">存続可能 Branch Appliance gateway または存続可能ブランチサーバーの外部ゲートウェイから egresses する音声ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="20824-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="20824-114">(「操作」のドキュメントの「 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md) 」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="20824-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="20824-115">中央サイトにあるバックアップレジストラープール (仲介サーバーと併置されている) を指すように、存続可能 Branch Appliance または存続可能 Branch Server gateway でバックアップ呼び出しルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="20824-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="20824-116">(存続可能 Branch Appliance または存続可能 Branch Server ベンダーのドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="20824-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="20824-117">このバックアップ通話ルートの設定は、存続可能 Branch Appliance または存続可能ブランチサーバーが使用できない場合 (たとえば、メンテナンスのため) にブランチユーザーへの着信呼び出しが動作するようにするために使用します。</span><span class="sxs-lookup"><span data-stu-id="20824-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="20824-118">存続可能ブランチアプライアンスまたは存続可能ブランチサーバー上のレジストラーと仲介サーバーが使用できず、ユーザーがセントラルサイトのバックアップレジストラープールに登録されている場合でも、ユーザーに着信呼び出しをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="20824-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="20824-119">**次のステップ**: [Lync Server 2013 でのボイスメール再ルーティング設定の構成](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="20824-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

