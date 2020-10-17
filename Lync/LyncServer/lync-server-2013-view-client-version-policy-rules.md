---
title: 'Lync Server 2013: クライアントバージョンポリシールールの表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a269ff6a90f95d76ddc9c230a3ce8a769977dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506554"
---
# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="c6b7d-102">Lync Server 2013 でクライアントバージョンポリシールールを表示する</span><span class="sxs-lookup"><span data-stu-id="c6b7d-102">View client version policy rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6b7d-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c6b7d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c6b7d-104">クライアントバージョンポリシーは、一連のクライアントバージョンポリシールールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="c6b7d-105">これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="c6b7d-106">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからクライアントバージョンポリシールールを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="c6b7d-107">Lync Server コントロールパネルを使用してクライアントバージョンポリシールールを表示するには</span><span class="sxs-lookup"><span data-stu-id="c6b7d-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c6b7d-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c6b7d-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c6b7d-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c6b7d-111">左側のナビゲーションバーで [ **クライアント**] をクリックし、[ **クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="c6b7d-112">[ **クライアントバージョンポリシー** ] ページで、表示するクライアントバージョンポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="c6b7d-113">ルールは [ **クライアントバージョンポリシーの編集** ] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="c6b7d-114">ルールの詳細を表示するには、ルールを選択し、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c6b7d-115">Windows PowerShell コマンドレットを使用してクライアントバージョンポリシールールを表示する</span><span class="sxs-lookup"><span data-stu-id="c6b7d-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c6b7d-116">Lync Server 管理シェルと **Get-CsClientVersionPolicyRule** コマンドレットを使用して、クライアントバージョンポリシールールを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="c6b7d-117">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c6b7d-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="c6b7d-119">クライアントバージョンポリシールールを表示するには</span><span class="sxs-lookup"><span data-stu-id="c6b7d-119">To view client version policy rules</span></span>

  - <span data-ttu-id="c6b7d-120">クライアントバージョンポリシールールを表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="c6b7d-121">これにより、構成済みの各ルールについて次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="c6b7d-122">詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) 」というヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b7d-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

