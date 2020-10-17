---
title: 'Lync Server 2013: 付録 A: コマンドレットを使用した存続可能ブランチアプライアンスの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e09cd7e0c5cc8bc20f50ba2c2ae5a1d912f949ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531624"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="7e2e1-102">付録 A: コマンドレットを使用して Lync Server 2013 で存続可能ブランチアプライアンスを展開する</span><span class="sxs-lookup"><span data-stu-id="7e2e1-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e2e1-103">_**トピックの最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="7e2e1-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="7e2e1-104">このトピックでは、Lync Server 管理シェルを使用して存続可能ブランチアプライアンスを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="7e2e1-105">中央サイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="7e2e1-106">存続可能 Branch アプライアンスをリモートで展開するには</span><span class="sxs-lookup"><span data-stu-id="7e2e1-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="7e2e1-107">新しいブランチサイトを追加するには、「 [Lync Server 2013 でブランチサイトをトポロジに追加](lync-server-2013-add-branch-sites-to-your-topology.md) する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="7e2e1-108">ブランチ サイトをドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="7e2e1-109">RTCUniversalSBATechnicians グループをローカルの Administrators グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="7e2e1-110">サーバーを再起動し、RTCUniversalSBATechnicians グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="7e2e1-111">Lync Server 管理シェルで、次のコマンドを入力します。プレースホルダーは、組織の正しい情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

