---
title: 'Lync Server 2013: グループ通話の集配番号をユーザーに割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="28164-102">グループ通話の集配番号を Lync Server 2013 のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="28164-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28164-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="28164-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="28164-104">グループ通話のピックアップグループ番号をコールパークの軌道テーブルに追加したら、グループをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="28164-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="28164-105">セカンダリ拡張機能のアクティブ化 (SEFAUtil) リソースキットツールを使用して、ユーザーに通話ピックアップグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="28164-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28164-106">ハイブリッド展開では、オンラインのユーザーにグループの通話ピックアップグループを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="28164-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="28164-107">自宅のユーザーはグループ通話のピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="28164-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="28164-108">つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="28164-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="28164-109">グループ通話のピックアップグループをユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="28164-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="28164-110">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="28164-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="28164-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="28164-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="28164-112">例:</span><span class="sxs-lookup"><span data-stu-id="28164-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28164-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="28164-113">See Also</span></span>


[<span data-ttu-id="28164-114">Lync Server 2013 のユーザーに対してグループ通話のピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="28164-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="28164-115">Lync Server 2013 のユーザーに対してグループ通話のピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="28164-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

