---
title: 'Lync Server 2013: 統合連絡先ストアでユーザーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b4c060cfce4e45f4736abcbc0d4c9d02b1abc1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528554"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="d91dd-102">Lync Server 2013 で統合連絡先ストアに対してユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="d91dd-102">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d91dd-103">_**トピックの最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="d91dd-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="d91dd-104">Lync Server 2013 を展開してトポロジを公開すると、既定では、すべてのユーザーに対して統合連絡先ストアが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d91dd-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="d91dd-105">Lync Server 2013 を展開した後に、統合連絡先ストアを有効にするために追加のアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d91dd-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="d91dd-106">ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d91dd-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="d91dd-107">この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d91dd-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="d91dd-108">統合連絡先ストアでユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d91dd-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="d91dd-109">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d91dd-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d91dd-110">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d91dd-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="d91dd-111">すべての Lync Server ユーザーに対して統合連絡先ストアをグローバルに有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d91dd-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="d91dd-112">統合連絡先ストアを特定のサイトのユーザーに対して有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d91dd-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="d91dd-113">例:</span><span class="sxs-lookup"><span data-stu-id="d91dd-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="d91dd-114">統合連絡先ストアをテナントごとに有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d91dd-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="d91dd-115">例:</span><span class="sxs-lookup"><span data-stu-id="d91dd-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="d91dd-116">統合連絡先ストアを特定のユーザーに対して有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d91dd-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d91dd-117">ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d91dd-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="d91dd-118">例:</span><span class="sxs-lookup"><span data-stu-id="d91dd-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d91dd-p102">前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを UCS Enabled Users<EM></EM> という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d91dd-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

