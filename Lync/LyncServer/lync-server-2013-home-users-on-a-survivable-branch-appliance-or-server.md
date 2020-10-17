---
title: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバー上のホームユーザー'
description: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバー上のホームユーザー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 124eb7a51a8d5ff672d720fdad8956f682e29090
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552783"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="1c24c-103">Lync Server 2013 の存続可能ブランチアプライアンスまたはサーバー上のホームユーザー</span><span class="sxs-lookup"><span data-stu-id="1c24c-103">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c24c-104">_**トピックの最終更新日:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="1c24c-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="1c24c-105">存続可能ブランチアプライアンスまたは存続可能ブランチサーバーでユーザーをホームにするプロセスは、フロントエンドプールでユーザーをホームにするプロセスに似ています。</span><span class="sxs-lookup"><span data-stu-id="1c24c-105">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="1c24c-106">中央サイトで存続可能 Branch Appliance または存続可能 Branch Server プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-106">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="1c24c-107">存続可能ブランチアプライアンスまたは存続可能ブランチサーバー上のホームユーザーに</span><span class="sxs-lookup"><span data-stu-id="1c24c-107">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="1c24c-108">ユーザーを存続可能ブランチサーバーまたは存続可能ブランチサーバーに移動する前に、Lync Server 管理シェルを開き、次のすべての手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-108">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="1c24c-109">コマンドレット **Test-CsPstnOutboundCall** を実行して、存続可能ブランチサーバーが実行中で、公衆交換電話網 (PSTN) 接続が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-109">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="1c24c-110">PSTN ゲートウェイのプロパティを変更する必要がある場合は、コマンドレット **Set-CsPstnGateway**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1c24c-110">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="1c24c-111">**Set-csvoicepolicy**コマンドレットを実行して、存続可能ブランチサーバーに所属するユーザーが適切な VoIP ルーティングポリシーを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-111">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="1c24c-112">VoIP ポリシーを変更する必要がある場合は、コマンドレット **set-csvoicepolicy**を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-112">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="1c24c-113">**Get-csvoicemailreroutingconfiguration**コマンドレットを実行して、ボイスメールの再ルーティング設定が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-113">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="1c24c-114">ボイスメールの再ルーティング設定を変更する必要がある場合は、 **get-csvoicemailreroutingconfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c24c-114">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="1c24c-115">Lync Server 管理シェルで、コマンドレットを実行して、ホームユーザーを **移動します** 。</span><span class="sxs-lookup"><span data-stu-id="1c24c-115">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c24c-116">また、Lync Server コントロールパネルを使用して、前提条件とホームユーザーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c24c-116">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1c24c-117">Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c24c-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c24c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c24c-118">See Also</span></span>


[<span data-ttu-id="1c24c-119">テスト-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="1c24c-119">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="1c24c-120">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="1c24c-120">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="1c24c-121">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1c24c-121">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="1c24c-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="1c24c-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

