---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる'
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="bc8a2-102">Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる</span><span class="sxs-lookup"><span data-stu-id="bc8a2-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc8a2-103">_**最終更新日:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="bc8a2-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="bc8a2-104">Survivable Branch Appliance または Survivable ブランチサーバーにユーザーをホームするプロセスは、フロントエンドプールでユーザーをホームにするプロセスと似ています。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="bc8a2-105">セントラルサイトで Survivable Branch Appliance または Survivable Branch Server の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="bc8a2-106">Survivable Branch Appliance または Survivable ブランチサーバー上のホームユーザーに</span><span class="sxs-lookup"><span data-stu-id="bc8a2-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="bc8a2-107">Survivable Branch Server または Survivable ブランチサーバーにユーザーを移動する前に、Lync Server 管理シェルを開き、次のすべての操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="bc8a2-108">コマンドレット**テスト-CsPstnOutboundCall**を実行して、Survivable Branch Server が実行されていて、公衆交換電話網 (PSTN) 接続が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="bc8a2-109">PSTN ゲートウェイのプロパティを変更する必要がある場合は、コマンドレットのセットされた**CsPstnGateway**を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="bc8a2-110">**CsVoicePolicy**コマンドレットを実行して、Survivable ブランチサーバーをホームにしているユーザーに適切な VoIP ルーティングポリシーが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="bc8a2-111">VoIP ポリシーを変更する必要がある場合は、コマンドレット**CsVoicePolicy**を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="bc8a2-112">**CsVoicemailReroutingConfiguration**コマンドレットを実行して、ボイスメールの再ルーティング設定が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="bc8a2-113">ボイスメールの再ルーティング設定を変更する必要がある場合は、コマンドレット**CsVoicemailReroutingConfiguration**を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="bc8a2-114">Lync Server 管理シェル**でコマンドレットを実行**して、ホームユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc8a2-115">Lync Server コントロールパネルを使用して、前提条件とホームユーザーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bc8a2-116">Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc8a2-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc8a2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc8a2-117">See Also</span></span>


[<span data-ttu-id="bc8a2-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="bc8a2-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="bc8a2-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="bc8a2-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="bc8a2-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc8a2-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="bc8a2-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="bc8a2-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

