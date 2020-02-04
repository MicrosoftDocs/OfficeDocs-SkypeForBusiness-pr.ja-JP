---
title: 'Lync Server 2013: 移行したユーザーのロールバック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8b8c53f835bbbaa363a91ef547dd1d301c8976
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="8e678-102">Lync Server 2013 での移行したユーザーのロールバック</span><span class="sxs-lookup"><span data-stu-id="8e678-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e678-103">_**最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="8e678-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="8e678-104">ユニファイド連絡先ストアの機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ、連絡先をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="8e678-105">ロールバックするには、ユーザーのポリシーを無効にしてから、 **CsUcsRollback**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8e678-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="8e678-106">**CsUcsRollback**のみを実行するだけでは、ポリシーが無効になっている場合に、統合された連絡先ストアの移行が再び開始されるため、永続的なロールバックを確実に行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="8e678-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="8e678-107">たとえば、exchange 2013 が Exchange 2010 にロールバックされたためにユーザーがロールバックされた場合、ユーザーのメールボックスは Exchange 2013 に移動されます。統合連絡先ストアの移行は、統合連絡先ストアの場合、ロールバック後7日後に開始されます。は、ユーザーサービスポリシーのユーザーに対してまだ有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8e678-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e678-108"><STRONG>ムーブグループのユーザー</STRONG>コマンドレットは、次のような場合に、ユーザーの連絡先ストアを Exchange 2013 から Lync Server 2013 に自動的にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8e678-109">ユーザーが Lync Server 2013 から Lync Server 2010 に移動された場合。</span><span class="sxs-lookup"><span data-stu-id="8e678-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="8e678-110">ユーザーが Lync Online からオンプレミスの Lync Server 2013 に移行される場合、またはその逆の場合。</span><span class="sxs-lookup"><span data-stu-id="8e678-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e678-p102">バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="8e678-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8e678-113">ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートした後、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</span><span class="sxs-lookup"><span data-stu-id="8e678-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="8e678-114">Exchange 2013 にユーザーを移行した後で userdata をエクスポートする場合は、移行をロールバックし、何らかの理由で移行後にデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</span><span class="sxs-lookup"><span data-stu-id="8e678-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e678-115">Exchange のメールボックスを exchange 2013 から Exchange 2010 に移動する前に、Exchange 管理者が、lync server のユーザーの連絡先を Exchange 2013 から Lync Server にロールバックしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e678-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="8e678-116">ユニファイド連絡先ストアの連絡先を Lync Server にロールバックするには、このセクションの後半の「ユニファイド連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e678-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="8e678-117">次の手順では、ユーザーの連絡先をロールバックする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8e678-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="8e678-118">ユーザーコマンドレットを使用**して Lync** server 2013 と lync server 2010 の間でユーザーを移動する場合は、ユーザーが lync server 2013 から lync server 2010 にユーザーを移動したときに、ユーザーの**移動**によって unifed の連絡先ストアが自動的にロールバックされるため、次の手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="8e678-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="8e678-119">**Move-CsUser**はユニファイド連絡先ストアポリシーを無効にしないため、ユーザーが Lync Server 2013 に戻ると、統合連絡先ストアへの移行が繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="8e678-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="8e678-120">Lync Server 2013 から Lync Server 2010 にユーザーの連絡先をロールバックするには</span><span class="sxs-lookup"><span data-stu-id="8e678-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="8e678-121">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8e678-122">ロールバックの後にユーザーが再移行しないように、統合連絡先ストアを無効にしてロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-122">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="8e678-123">(この手順は、ユーザーが今後 remigrate しないようにする場合にのみ実行してください。)個々のユーザーに対してユニファイド連絡先ストアを無効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8e678-123">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="8e678-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e678-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="8e678-125">Lync server 2013 から Lync Server 2010 にユーザーを移動する前に、Lync Server で指定したユーザーの友人リストをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e678-126">この手順を省略すると、友人リストは失われます。</span><span class="sxs-lookup"><span data-stu-id="8e678-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="8e678-127">指定したユーザーをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-127">Roll back the specified users.</span></span> <span data-ttu-id="8e678-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8e678-128">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="8e678-129">例:</span><span class="sxs-lookup"><span data-stu-id="8e678-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e678-130">ロールバックを強制するには、– Force オプションを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="8e678-130">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="8e678-131">このオプションを使用すると、ユーザーの連絡先が失われます。</span><span class="sxs-lookup"><span data-stu-id="8e678-131">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="8e678-132">統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには</span><span class="sxs-lookup"><span data-stu-id="8e678-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="8e678-133">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8e678-134">ロールバックの後にユーザーが再移行しないように、統合連絡先ストアを無効にしてロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-134">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="8e678-135">個々のユーザーに対してユニファイド連絡先ストアを無効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8e678-135">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="8e678-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e678-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="8e678-137">指定したユーザーをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="8e678-137">Roll back the specified users.</span></span> <span data-ttu-id="8e678-138">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8e678-138">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="8e678-139">例:</span><span class="sxs-lookup"><span data-stu-id="8e678-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e678-140">まず、Lync Server ユーザーをロールバックして、Exchange 2013 メールボックスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e678-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="8e678-141">Exchange 管理者は、Lync Server のロールバックが完了するまで、Exchange のロールバックがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8e678-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="8e678-142">ロールバックを強制するには、– Force オプションを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="8e678-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="8e678-143">このオプションを使用すると、ユーザーの連絡先が失われます。</span><span class="sxs-lookup"><span data-stu-id="8e678-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="8e678-144">ユーザーを Lync Server にロールバックすると、exchange 管理者は exchange 2013 から exchange 2010 に Exchange ユーザーをロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e678-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

