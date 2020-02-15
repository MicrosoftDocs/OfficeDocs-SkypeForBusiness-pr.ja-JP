---
title: 'Lync Server 2013: ユーザーのグループ通話ピックアップを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7e744f42368cd02b197533b84352f8f0477d848
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="9c2c3-102">Lync Server 2013 でユーザーのグループ通話ピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="9c2c3-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c2c3-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9c2c3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9c2c3-104">SEFAUtil リソースキットツールを使用して、ユーザーのグループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9c2c3-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="9c2c3-105">グループ通話ピックアップを有効にするには、コールパークオービットテーブルで種類が GroupPickup のグループ番号がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c2c3-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="9c2c3-106">SEFAUtil を実行するときに、/enablegrouppickup パラメーターを使用して、通話ピックアップグループ番号を割り当て、グループ通話ピックアップを同時に有効にします。</span><span class="sxs-lookup"><span data-stu-id="9c2c3-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="9c2c3-107">ユーザーのグループ通話ピックアップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="9c2c3-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="9c2c3-108">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="9c2c3-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="9c2c3-109">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c2c3-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="9c2c3-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c2c3-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c2c3-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c2c3-111">See Also</span></span>


[<span data-ttu-id="9c2c3-112">Lync Server 2013 でグループ通話ピックアップ番号をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9c2c3-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="9c2c3-113">Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="9c2c3-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

