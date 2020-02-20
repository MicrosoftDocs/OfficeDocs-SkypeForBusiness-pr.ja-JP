---
title: 'Lync Server 2013: 移行されたユーザーのロールバック'
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
ms.openlocfilehash: dbc2c46b462ec50c1f5796a9a6a03cd39f7b44dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="2b854-102">Lync Server 2013 で移行されたユーザーのロールバック</span><span class="sxs-lookup"><span data-stu-id="2b854-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b854-103">_**トピックの最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="2b854-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="2b854-104">統合連絡先ストア機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻した場合にのみ、連絡先をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="2b854-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="2b854-105">ロールバックするには、ユーザーのポリシーを無効にしてから、 **invoke-csucsrollback**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b854-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="2b854-106">**Invoke-csucsrollback**のみを実行するだけでは、ポリシーが無効になっていない場合に、統合連絡先ストアの移行が再び開始されるので、永続的なロールバックを保証するだけでは十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="2b854-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="2b854-107">たとえば、Exchange 2013 が Exchange 2010 にロールバックされたためにユーザーがロールバックされた場合に、ユーザーのメールボックスが Exchange 2013 に移動されると、統合連絡先ストアの移行は、統合された後7日後に開始されます (統合連絡先ストア)は、ユーザーサービスポリシーのユーザーに対して引き続き有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2b854-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b854-108">次の状況では、<STRONG>移動-csuser</STRONG>コマンドレットによって、ユーザーの連絡先ストアが Exchange 2013 から Lync Server 2013 に自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="2b854-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2b854-109">ユーザーが Lync Server 2013 から Lync Server 2010 に移動されたとき。</span><span class="sxs-lookup"><span data-stu-id="2b854-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="2b854-110">ユーザーが Lync Online から社内の Lync Server 2013 に移動された場合や、その逆の場合など、ユーザーがクロスプレミスで移行されるとき。</span><span class="sxs-lookup"><span data-stu-id="2b854-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b854-p102">バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="2b854-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2b854-113">ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートした後、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</span><span class="sxs-lookup"><span data-stu-id="2b854-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="2b854-114">ユーザーを Exchange 2013 に移行した後に userdata をエクスポートする場合は、移行をロールバックし、何らかの理由で移行後にデータをインポートした後、統合連絡先ストアのデータと連絡先リストが破損します。</span><span class="sxs-lookup"><span data-stu-id="2b854-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b854-115">Exchange 2013 から exchange 2010 に Exchange メールボックスを移動する前に、Exchange 管理者は、まず lync server ユーザーの連絡先を Exchange 2013 から Lync Server にロールバックしたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b854-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="2b854-116">統合連絡先ストアの連絡先を Lync Server にロールバックするには、このセクションで後述する「統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b854-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="2b854-117">次の手順では、ユーザーの連絡先をロールバックする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="2b854-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="2b854-118">**Move-csuser**コマンドレットを使用して lync server 2013 と lync server 2010 間でユーザーを移動する場合は、lync server の2013から Lync 2010 server へのユーザーの移動時に、ユーザーコマンドレットが自動的に unifed 連絡先ストアをロール**バックするの**で、次の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="2b854-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="2b854-119">**Move-CsUser**は、統合連絡先ストアポリシーを無効にしないので、ユーザーが Lync Server 2013 に戻った場合、統合連絡先ストアへの移行は繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="2b854-120">Lync Server 2013 から Lync Server 2010 にユーザーの連絡先をロールバックするには</span><span class="sxs-lookup"><span data-stu-id="2b854-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="2b854-121">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b854-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2b854-p105">ロールバック後にユーザーの再移行が行われないように、ロールバックするユーザーに対して統合連絡先ストアを無効にします (この手順は、将来ユーザーが再移行されないようにしたい場合にだけ実行します)。統合連絡先ストアを個別のユーザーに対して無効にするには、コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2b854-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="2b854-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2b854-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="2b854-125">Lync server 2013 から lync Server 2010 にユーザーを移動する前に、Lync Server で指定されたユーザーの友人リストをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="2b854-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2b854-126">このステップを省略すると、バディ リストが失われます。</span><span class="sxs-lookup"><span data-stu-id="2b854-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="2b854-p106">指定したユーザーをロールバックします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2b854-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="2b854-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2b854-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2b854-p107">–Force オプションを使用して強制的にロールバックすることはお勧めしません。このオプションを使用すると、ユーザーの連絡先が失われます。</span><span class="sxs-lookup"><span data-stu-id="2b854-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="2b854-132">統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには</span><span class="sxs-lookup"><span data-stu-id="2b854-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="2b854-133">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b854-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2b854-p108">ロールバック後にユーザーの再移行が行われないように、ロールバックするユーザーに対して統合連絡先ストアを無効にします。統合連絡先ストアを個別のユーザーに対して無効にするには、コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2b854-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="2b854-136">例:</span><span class="sxs-lookup"><span data-stu-id="2b854-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="2b854-p109">指定したユーザーをロールバックします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2b854-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="2b854-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2b854-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2b854-140">最初に、Lync Server ユーザーをロールバックしてから、Exchange 2013 メールボックスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b854-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="2b854-141">Exchange 管理者は、Lync Server のロールバックが完了するまで Exchange のロールバックをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2b854-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="2b854-142">–Force オプションを使用して強制的にロールバックすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="2b854-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="2b854-143">このオプションを使用すると、ユーザーの連絡先が失われます。</span><span class="sxs-lookup"><span data-stu-id="2b854-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="2b854-144">ユーザーを Lync Server にロールバックすると、exchange 管理者は exchange 2013 から exchange 2010 に Exchange ユーザーをロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b854-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

