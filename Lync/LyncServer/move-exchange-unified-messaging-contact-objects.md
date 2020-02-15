---
title: Exchange ユニファイドメッセージング連絡先オブジェクトの移動
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c02e391fa66084a27e3790ccaf42753bcaeaa16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="6cfec-102">Exchange ユニファイドメッセージング連絡先オブジェクトの移動</span><span class="sxs-lookup"><span data-stu-id="6cfec-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cfec-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6cfec-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6cfec-104">自動応答 (AA) およびサブスクライバーアクセス (SA) の連絡先オブジェクトを新しい Lync Server 2013 展開に移行するには、まず、従来の Office Communications Server 2007 R2 展開から新しい Lync Server 2013 展開にオブジェクトを移動するには、まず、 **Get-csexumcontact**および**Move-csexumcontact**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="6cfec-105">Exchange サーバーでは、次のように、 **Exchucutil** Windows PowerShell スクリプトを実行して、新しく展開された Lync プールに対して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6cfec-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="6cfec-106">ユニファイド メッセージング IP ゲートウェイに追加します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="6cfec-107">ユニファイド メッセージング ハント グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cfec-p102"><STRONG>Get-CsExUmContact</STRONG> および <STRONG>Move-CsExUmContact</STRONG> コマンドレットを使用するには、RTCUniversalUserAdmins グループのメンバーであり、連絡先オブジェクトを格納する組織単位 (OU) に対する OU アクセス許可を持っている必要があります。OU アクセス許可は <STRONG>Grant-OUPermission</STRONG> コマンドレットを使用して付与できます。</span><span class="sxs-lookup"><span data-stu-id="6cfec-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="6cfec-110">Lync Server 管理シェルを使用して連絡先オブジェクトを移動するには</span><span class="sxs-lookup"><span data-stu-id="6cfec-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="6cfec-111">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cfec-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="6cfec-112">コマンドラインで、Exchange UM に登録されている各プール (pool1.contoso.net は、Office Communications Server 2007 R2 展開からのプールで、pool2.contoso.net は Lync Server 2013 展開からのプールである) に対して、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="6cfec-113">連絡先オブジェクトが移動されたことを確認するには、**Get-CsExumContact** コマンドレットを実行し、**RegistrarPool** が新しいプールを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="6cfec-114">Windows PowerShell の ExchUCUtil スクリプトを実行するには</span><span class="sxs-lookup"><span data-stu-id="6cfec-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="6cfec-115">Exchange 組織管理者特権のあるユーザーとして Exchange UM Server にログオンします。</span><span class="sxs-lookup"><span data-stu-id="6cfec-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="6cfec-116">ExchUCUtil Windows PowerShell スクリプトに移動します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="6cfec-117">Exchange 2007 では、ExchUCUtil. ps1 は次の場所にあります。 **% Program\\Files\\%\\\\Microsoft Exchange Server Scripts exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="6cfec-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="6cfec-118">Exchange 2010 では、ExchUCUtil. ps1 は次の場所にあります。 **% Program\\Files\\%\\\\\\Microsoft Exchange Server V14 Scripts exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="6cfec-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="6cfec-119">Exchange が単一のフォレストに展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="6cfec-120">Exchange が複数のフォレストに展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="6cfec-121">フォレスト FQDN には、Lync Server 2013 が展開されているフォレストを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cfec-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6cfec-122">exchucutil.ps1 を実行した<EM></EM>後で、<STRONG>Lync サーバー フロントエンド</STRONG> サービス (rtcsrv.exe) を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="6cfec-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="6cfec-123">それ以外の場合、Lync Server 2013 は、トポロジ内のユニファイドメッセージングを検出しません。</span><span class="sxs-lookup"><span data-stu-id="6cfec-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

