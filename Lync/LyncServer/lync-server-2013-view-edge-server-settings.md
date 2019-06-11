---
title: 'Lync Server 2013: エッジサーバーの設定を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="b3501-102">Lync Server 2013 でエッジサーバーの設定を表示する</span><span class="sxs-lookup"><span data-stu-id="b3501-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3501-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b3501-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="b3501-104">一般的なエッジサーバー構成は、構成管理データベースのデータに対して検証する必要があります。これにより、すべての変更が、定義された変更管理手順に従って文書化されていることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="b3501-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="b3501-105">追加のチェックには、次のセクションで説明されているようなものが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3501-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="b3501-106">許可/禁止リストを確認する</span><span class="sxs-lookup"><span data-stu-id="b3501-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="b3501-107">リストされた名前空間が有効であるかどうかを判断するには、フェデレーションドメインの SIP URI "Allow" および "Block" リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3501-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="b3501-108">Windows PowerShell を使用して、許可リストとブロックリストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b3501-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="b3501-109">[許可ドメイン] リストのドメインを確認するには、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3501-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="b3501-110">このコマンドは、許可ドメインリストのドメインについて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b3501-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="b3501-111">Id: contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3501-111">Identity : contoso.com</span></span>

<span data-ttu-id="b3501-112">Domain: contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3501-112">Domain : contoso.com</span></span>

<span data-ttu-id="b3501-113">ProxyFqdn:</span><span class="sxs-lookup"><span data-stu-id="b3501-113">ProxyFqdn :</span></span>

<span data-ttu-id="b3501-114">注釈</span><span class="sxs-lookup"><span data-stu-id="b3501-114">Comment :</span></span>

<span data-ttu-id="b3501-115">マークフォーム Onitor: False</span><span class="sxs-lookup"><span data-stu-id="b3501-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="b3501-116">注釈</span><span class="sxs-lookup"><span data-stu-id="b3501-116">Comment :</span></span>

<span data-ttu-id="b3501-117">ブロックドメインリストのドメインを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3501-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="b3501-118">次に、ブロックした各ドメインについて、次のような情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b3501-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="b3501-119">Id: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b3501-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="b3501-120">Domain: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b3501-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="b3501-121">Windows PowerShell でも、許可ドメインリストのドメインに接続できるかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b3501-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="b3501-122">たとえば、次のコマンドは、Edge サーバー (TargetFqdn) とフェデレーションドメイン contoso.com の間の接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="b3501-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="b3501-123">このコマンドを実行すると、エッジサーバーと、許可ドメインの一覧で見つかったすべてのドメインの間の接続が確認されます。</span><span class="sxs-lookup"><span data-stu-id="b3501-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="b3501-124">複数のエッジサーバーが同じであることを確認する</span><span class="sxs-lookup"><span data-stu-id="b3501-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="b3501-125">負荷分散アレイに複数のエッジサーバーが展開されている場合は、配列内のすべてのエッジサーバーが同じ方法で構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3501-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="b3501-126">[コンピューターの管理] スナップイン用の Lync Server 2013 拡張機能の詳細ウィンドウで、エッジサーバーの設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b3501-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3501-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3501-127">See Also</span></span>


[<span data-ttu-id="b3501-128">購入-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="b3501-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="b3501-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="b3501-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="b3501-130">テスト-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="b3501-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

