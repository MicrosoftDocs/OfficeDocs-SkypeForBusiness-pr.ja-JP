---
title: 'Lync Server 2013: グループ通話ピックアップ番号をユーザーに割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b437b9da1abaa62d34a177c0188396c30bf7a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="a0db2-102">Lync Server 2013 でグループ通話ピックアップ番号をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a0db2-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0db2-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a0db2-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a0db2-104">グループ通話ピックアップグループ番号をコールパークオービットテーブルに追加すると、グループをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a0db2-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="a0db2-105">代理の拡張機能のアクティブ化 (SEFAUtil) リソースキットツールを使用して、ユーザーに通話ピックアップグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a0db2-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0db2-106">ハイブリッド展開では、online に所属しているユーザーにグループ通話ピックアップグループを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="a0db2-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="a0db2-107">オンラインに所属しているユーザーは、グループ通話ピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="a0db2-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="a0db2-108">つまり、他のユーザーはその通話に応答できないため、他のユーザーの呼び出しに応答できません。</span><span class="sxs-lookup"><span data-stu-id="a0db2-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="a0db2-109">グループの通話ピックアップグループをユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="a0db2-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="a0db2-110">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="a0db2-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="a0db2-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0db2-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="a0db2-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a0db2-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0db2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0db2-113">See Also</span></span>


[<span data-ttu-id="a0db2-114">Lync Server 2013 でユーザーのグループ通話ピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="a0db2-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="a0db2-115">Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="a0db2-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

