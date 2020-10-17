---
title: 'Lync Server 2013: エッジサーバーの設定の表示'
description: 'Lync Server 2013: エッジサーバーの設定を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4318b8c97f53f267bb79953af504977f6437214d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569683"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="7862a-103">Lync Server 2013 でのエッジサーバーの設定の表示</span><span class="sxs-lookup"><span data-stu-id="7862a-103">View Edge Server settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7862a-104">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="7862a-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="7862a-105">一般的なエッジサーバー構成は、構成管理データベース内のデータに対して確認する必要があります。これは、定義された変更管理手順に従ってすべての変更が記録されていることを保証するためです。</span><span class="sxs-lookup"><span data-stu-id="7862a-105">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="7862a-106">その他のチェックには、以下のセクションで説明するものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7862a-106">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="7862a-107">許可/禁止リストを確認する</span><span class="sxs-lookup"><span data-stu-id="7862a-107">Verify the Allow and block lists</span></span>

<span data-ttu-id="7862a-108">リストされている名前空間が有効かどうかを確認するには、フェデレーションドメインの SIP URI "Allow" および "Block" リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="7862a-108">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="7862a-109">許可またはブロックされたリストを表示するには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7862a-109">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="7862a-110">許可されたドメインの一覧でドメインを確認するには、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7862a-110">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="7862a-111">このコマンドは、許可されたドメインリストのドメインについて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7862a-111">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="7862a-112">Identity: contoso.com</span><span class="sxs-lookup"><span data-stu-id="7862a-112">Identity : contoso.com</span></span>

<span data-ttu-id="7862a-113">ドメイン: contoso.com</span><span class="sxs-lookup"><span data-stu-id="7862a-113">Domain : contoso.com</span></span>

<span data-ttu-id="7862a-114">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="7862a-114">ProxyFqdn :</span></span>

<span data-ttu-id="7862a-115">Comment</span><span class="sxs-lookup"><span data-stu-id="7862a-115">Comment :</span></span>

<span data-ttu-id="7862a-116">MarkForMonitoring: False</span><span class="sxs-lookup"><span data-stu-id="7862a-116">MarkForMonitoring : False</span></span>

<span data-ttu-id="7862a-117">Comment</span><span class="sxs-lookup"><span data-stu-id="7862a-117">Comment :</span></span>

<span data-ttu-id="7862a-118">禁止ドメインリストのドメインを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7862a-118">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="7862a-119">その後、ブロックされた各ドメインについて、次のような情報を受信することになります。</span><span class="sxs-lookup"><span data-stu-id="7862a-119">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="7862a-120">Identity: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="7862a-120">Identity : tailspintoys.com</span></span>

<span data-ttu-id="7862a-121">ドメイン: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="7862a-121">Domain : tailspintoys.com</span></span>

<span data-ttu-id="7862a-122">また、Windows PowerShell では、許可されたドメインリストのドメインに接続できることを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="7862a-122">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="7862a-123">たとえば、次のコマンドは、エッジサーバー (TargetFqdn) とフェデレーションドメイン contoso.com の間の接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="7862a-123">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="7862a-124">次のコマンドを実行すると、エッジサーバーと、許可されたドメインの一覧にあるすべてのドメインとの間の接続が確認されます。</span><span class="sxs-lookup"><span data-stu-id="7862a-124">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="7862a-125">複数のエッジサーバーが同一であることを確認する</span><span class="sxs-lookup"><span data-stu-id="7862a-125">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="7862a-126">複数のエッジサーバーが負荷分散アレイに展開されている場合は、アレイ内のすべてのエッジサーバーが同じ方法で構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7862a-126">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="7862a-127">エッジサーバーの設定は、[コンピューターの管理] スナップインの [Lync Server 2013] 拡張機能の詳細ウィンドウで確認できます。</span><span class="sxs-lookup"><span data-stu-id="7862a-127">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7862a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7862a-128">See Also</span></span>


[<span data-ttu-id="7862a-129">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="7862a-129">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="7862a-130">Get-csblockeddomain</span><span class="sxs-lookup"><span data-stu-id="7862a-130">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="7862a-131">Test-csfederatedpartner</span><span class="sxs-lookup"><span data-stu-id="7862a-131">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

