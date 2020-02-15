---
title: 'Lync Server 2013: ユーザーのグループ通話ピックアップを無効にする'
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
ms.openlocfilehash: c03242cf0b3521dada944ccaba30946306c1ff24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="1356b-102">Lync Server 2013 でユーザーのグループ通話ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="1356b-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1356b-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="1356b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="1356b-104">ユーザーのグループ通話ピックアップを無効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1356b-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1356b-105">ユーザーのグループ通話ピックアップを無効にしても、ユーザーに割り当てられていた通話ピックアップグループ番号は保持されません。</span><span class="sxs-lookup"><span data-stu-id="1356b-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="1356b-106">その後、そのユーザーのグループ通話ピックアップを再度有効にする場合は、もう一度、/enablegrouppickup パラメーターを使用して、通話ピックアップグループ番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1356b-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="1356b-107">ユーザーのグループ通話ピックアップを無効にするには</span><span class="sxs-lookup"><span data-stu-id="1356b-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="1356b-108">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="1356b-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="1356b-109">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1356b-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="1356b-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1356b-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1356b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1356b-111">See Also</span></span>


[<span data-ttu-id="1356b-112">Lync Server 2013 でグループ通話ピックアップ番号をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="1356b-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="1356b-113">Lync Server 2013 でユーザーのグループ通話ピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="1356b-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

