---
title: Exchange ユニファイドメッセージングの連絡先オブジェクトを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="dc652-102">Exchange ユニファイドメッセージングの連絡先オブジェクトを移動する</span><span class="sxs-lookup"><span data-stu-id="dc652-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc652-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="dc652-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="dc652-104">自動応答 (AA) および加入者アクセス (SA) 連絡先オブジェクトを新しい Lync Server 2013 の展開に移行するには、まず、**従来の Office Communications Server 2007 R2 の展開から新しい Lync server 2013 展開にオブジェクトを移動します。CsExUmContact**と**移動-csexumcontact**コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="dc652-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="dc652-105">Exchange サーバーで、 **Exchucutil** Windows PowerShell スクリプトを実行して、新しく展開された Lync プールに対して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dc652-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="dc652-106">ユニファイドメッセージング IP ゲートウェイに追加します。</span><span class="sxs-lookup"><span data-stu-id="dc652-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="dc652-107">ユニファイドメッセージングハントグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="dc652-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc652-108"><STRONG>Get-csexumcontact</STRONG>および<STRONG>Move-csexumcontact</STRONG>コマンドレットを使用するには、RTCUniversalUserAdmins グループのメンバーであり、連絡先オブジェクトが保存されている OU に対して組織単位 (ou) のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc652-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="dc652-109">権限付与は、 <STRONG>Grant permission</STRONG>コマンドレットを使って行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dc652-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="dc652-110">Lync Server 管理シェルを使用して連絡先オブジェクトを移動するには</span><span class="sxs-lookup"><span data-stu-id="dc652-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="dc652-111">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc652-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="dc652-112">Exchange UM に登録されている各プール (pool1.contoso.net は、Office Communications Server 2007 R2 の展開からのプールであり、pool2.contoso.net は Lync Server 2013 の展開からのプールである) には、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="dc652-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="dc652-113">連絡先オブジェクトが移動されたことを確認する\*\*\*\* には、 **RegistrarPool**コマンドレットを実行し、新しいプールをポイントしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc652-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="dc652-114">ExchUCUtil Windows PowerShell スクリプトを実行するには</span><span class="sxs-lookup"><span data-stu-id="dc652-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="dc652-115">Exchange の組織管理者権限を持つユーザーとして Exchange UM サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc652-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="dc652-116">ExchUCUtil Windows PowerShell スクリプトに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc652-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="dc652-117">Exchange 2007 では、ExchUCUtil は次の場所にあります。 **%\\Program\\Files%\\Microsoft\\Exchange Server スクリプト exchucutil**</span><span class="sxs-lookup"><span data-stu-id="dc652-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="dc652-118">Exchange 2010 では、ExchUCUtil は次の場所にあります: **%\\Program\\Files%\\Microsoft\\Exchange\\Server V14 スクリプト exchucutil**</span><span class="sxs-lookup"><span data-stu-id="dc652-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="dc652-119">1つのフォレストに Exchange が展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="dc652-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="dc652-120">または、複数のフォレストに Exchange が展開されている場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="dc652-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="dc652-121">ここで、[フォレスト FQDN の指定は Lync Server 2013 が展開されているフォレストを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc652-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dc652-122">Exchucutil を実行し<EM>た後</EM>、必ず<STRONG>Lync Server のフロントエンド</STRONG>サービス (rtcsrv) を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="dc652-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="dc652-123">そうしないと、Lync Server 2013 は、トポロジでユニファイドメッセージングを検出しません。</span><span class="sxs-lookup"><span data-stu-id="dc652-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

