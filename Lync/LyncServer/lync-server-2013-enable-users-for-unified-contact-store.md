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
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="aecf7-102">Lync Server 2013 の統合連絡先ストアでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="aecf7-102">Enable users for unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aecf7-103">_**最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="aecf7-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="aecf7-104">Lync Server 2013 を展開してトポロジを公開すると、既定では、統合連絡先ストアがすべてのユーザーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="aecf7-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="aecf7-105">Lync Server 2013 を展開した後、ユニファイド連絡先ストアを有効にするために、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aecf7-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="aecf7-106">ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="aecf7-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="aecf7-107">この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="aecf7-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="aecf7-108">統合連絡先ストアでユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="aecf7-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="aecf7-109">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="aecf7-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="aecf7-110">次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="aecf7-111">すべての Lync Server ユーザーに対して、統合された連絡先ストアをグローバルに有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="aecf7-112">特定のサイトのユーザーに対してユニファイド連絡先ストアを有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="aecf7-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="aecf7-114">テナントを使用してユニファイド連絡先ストアを有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="aecf7-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="aecf7-116">特定のユーザーに対してユニファイド連絡先ストアを有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aecf7-117">ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="aecf7-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="aecf7-118">例:</span><span class="sxs-lookup"><span data-stu-id="aecf7-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aecf7-p102">前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを <EM>UCS Enabled Users</EM> という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="aecf7-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

