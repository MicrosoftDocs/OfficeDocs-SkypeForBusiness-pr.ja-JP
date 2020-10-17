---
title: 'Lync Server 2013: コマンドレットを使用してフォレストの準備を元に戻す'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e3104f07934e590dc22ac9f5000601bc8166b6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535794"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="9cba1-102">コマンドレットを使用して Lync Server 2013 のフォレストの準備を元に戻す</span><span class="sxs-lookup"><span data-stu-id="9cba1-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cba1-103">_**トピックの最終更新日:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="9cba1-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="9cba1-104">フォレストの準備手順を元に戻すには、 **Disable-CsAdForest** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9cba1-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9cba1-105">以前のバージョンの Lync Server が展開されている環境で、 <STRONG>Disable-CsAdForest</STRONG> コマンドレットを実行すると、以前のバージョンのグローバル設定も削除されます。</span><span class="sxs-lookup"><span data-stu-id="9cba1-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="9cba1-106">コマンドレットを使用してフォレストの準備を元に戻すには</span><span class="sxs-lookup"><span data-stu-id="9cba1-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="9cba1-107">ドメインに参加しているコンピューターに、フォレストのルート ドメインの Domain Admins グループ メンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="9cba1-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="9cba1-108">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cba1-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9cba1-109">実行</span><span class="sxs-lookup"><span data-stu-id="9cba1-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="9cba1-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9cba1-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="9cba1-111">Force パラメーターは、タスクを強制的に実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cba1-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="9cba1-112">このパラメーターが存在しない場合、フォレスト内の1つのドメインが Lync Server 2013 に対してまだ準備されている場合、コマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9cba1-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="9cba1-113">Force パラメーターが指定されている場合、フォレスト内の他のドメインの状態に関係なく、アクションは続行されます。</span><span class="sxs-lookup"><span data-stu-id="9cba1-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="9cba1-114">GroupDomain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="9cba1-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9cba1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cba1-115">See Also</span></span>


[<span data-ttu-id="9cba1-116">Lync Server 2013 のフォレストの準備の実行</span><span class="sxs-lookup"><span data-stu-id="9cba1-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="9cba1-117">Lync Server 2013 のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="9cba1-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

