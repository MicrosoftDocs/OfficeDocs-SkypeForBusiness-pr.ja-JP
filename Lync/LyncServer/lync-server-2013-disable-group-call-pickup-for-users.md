---
title: 'Lync Server 2013: グループ通話のピックアップをユーザーに対して無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="4d145-102">Lync Server 2013 のユーザーに対してグループ通話のピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="4d145-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d145-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="4d145-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="4d145-104">次の手順を使用して、ユーザーのグループ通話のピックアップを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4d145-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d145-105">グループ通話のピックアップをユーザーに対して無効にしても、そのユーザーに割り当てられていた通話ピックアップグループ番号は保持されません。</span><span class="sxs-lookup"><span data-stu-id="4d145-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="4d145-106">そのユーザに対してグループ通話のピックアップを再び有効にする必要がある場合は、/enablegrouppickup パラメーターを使用して、もう一度通話ピックアップグループ番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d145-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="4d145-107">グループ通話のピックアップをユーザーに対して無効にするには</span><span class="sxs-lookup"><span data-stu-id="4d145-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="4d145-108">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="4d145-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="4d145-109">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d145-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="4d145-110">例:</span><span class="sxs-lookup"><span data-stu-id="4d145-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d145-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d145-111">See Also</span></span>


[<span data-ttu-id="4d145-112">グループ通話の集配番号を Lync Server 2013 のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d145-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="4d145-113">Lync Server 2013 のユーザーに対してグループ通話のピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="4d145-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

