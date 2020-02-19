---
title: 'Lync Server 2013: ユーザーのグループ通話ピックアップの有効化とグループ番号の割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e83972d95956a0ed2bd44f08ba8787c46118730
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="91bd4-102">Lync Server 2013 のユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="91bd4-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91bd4-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="91bd4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="91bd4-104">呼び出しピックアップグループ番号をコールパークオービットテーブルに追加したら、グループ番号をユーザーに割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="91bd4-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="91bd4-105">第2の拡張機能のアクティブ化 (SEFAUtil) リソースキットツールを使用して、グループ番号を割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="91bd4-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91bd4-106">ハイブリッド展開では、online に所属しているユーザーにグループ通話ピックアップグループを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="91bd4-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="91bd4-107">オンラインに所属しているユーザーは、グループ通話ピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="91bd4-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="91bd4-108">つまり、他のユーザーはその通話に応答できないため、他のユーザーの呼び出しに応答できません。</span><span class="sxs-lookup"><span data-stu-id="91bd4-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="91bd4-109">グループ番号を割り当てて、ユーザーのグループ通話ピックアップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="91bd4-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="91bd4-110">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="91bd4-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="91bd4-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="91bd4-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="91bd4-112">たとえば、グループ番号199をユーザーに割り当てるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="91bd4-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91bd4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="91bd4-113">See Also</span></span>


[<span data-ttu-id="91bd4-114">Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="91bd4-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

