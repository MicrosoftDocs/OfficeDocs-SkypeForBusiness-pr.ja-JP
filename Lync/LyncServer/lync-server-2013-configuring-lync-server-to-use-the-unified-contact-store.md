---
title: 'Lync Server 2013: 統合連絡先ストアを使用するように Lync Server を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21e39b9584dfc274e9cf525db85d50df6188fac0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="ae276-102">統合連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="ae276-102">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae276-103">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="ae276-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="ae276-104">統合連絡先ストアを使用すると、ユーザーは1つの連絡先リストを管理し、Microsoft Lync 2013、Microsoft Outlook 2013、Microsoft Outlook Web App 2013 などの複数のアプリケーションで連絡先を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae276-104">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="ae276-105">ユーザーに対して統合連絡先ストアを有効にすると、ユーザーの連絡先は Microsoft Lync Server 2013 に保存されず、SIP プロトコルを使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-105">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="ae276-106">代わりに、その連絡先は Microsoft Exchange Server 2013 に格納され、Exchange Web サービスを使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-106">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae276-107">技術的には、連絡先情報は、ユーザーの Exchange 2013 メールボックスにあるペアのフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-107">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="ae276-108">連絡先自体は、エンドユーザーに表示される Lync の連絡先という名前のフォルダーに保存されます。連絡先に関するメタデータは、エンドユーザーには表示されないサブフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-108">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="ae276-109">ユーザーに対して統合連絡先ストアを有効にする</span><span class="sxs-lookup"><span data-stu-id="ae276-109">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="ae276-110">Lync Server 2013 と Exchange 2013 の間のサーバー間認証が既に構成されている場合は、統合連絡先ストアの使用も有効になっています。追加のサーバー構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ae276-110">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="ae276-111">ただし、ユーザーの連絡先を統合連絡先ストアに移動するために、追加のユーザー アカウント構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae276-111">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="ae276-112">既定では、ユーザーの連絡先は、統合連絡先ストアではなく、Lync Server に保持されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-112">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="ae276-113">統合連絡先ストアへのアクセスは、Lync Server ユーザーサービスポリシーを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-113">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="ae276-114">ユーザーサーバーポリシーには、1つのプロパティのみがあります (UcsAllowed)。このプロパティは、ユーザーの連絡先が格納されている場所を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-114">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="ae276-115">UcsAllowed が True ($True) に設定されているユーザーサービスポリシーによってユーザーが管理されている場合は、ユーザーの連絡先が統合連絡先ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-115">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="ae276-116">ユーザーが、UcsAllowed が False ($False) に設定されているユーザーサービスポリシーで管理されている場合、その連絡先は Lync Server に保存されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-116">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="ae276-117">Lync Server 2013 をインストールすると、(グローバルスコープで構成されている) 単一のユーザーサービスポリシーもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ae276-117">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="ae276-118">このポリシーの UcsAllowed 値は True に設定されています。つまり、既定では、ユーザーの連絡先が統合連絡先ストアに保存されます (これが展開および構成されていることが前提です)。</span><span class="sxs-lookup"><span data-stu-id="ae276-118">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="ae276-119">すべてのユーザーの連絡先を統合連絡先ストアに移行する場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae276-119">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="ae276-120">すべての連絡先を統合連絡先ストアに移行しない場合は、グローバルポリシーの UcsAllowed プロパティを False に設定することによって、すべてのユーザーの統合連絡先ストアを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ae276-120">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="ae276-121">グローバルポリシーで統合連絡先ストアを無効にした後、統合連絡先ストアの使用を有効にするユーザーごとのポリシーを作成できます。これにより、他のユーザーが引き続き Lync Server に連絡先を保持しながら、一部のユーザーに自分の連絡先を統合連絡先ストアに保持させることができます。</span><span class="sxs-lookup"><span data-stu-id="ae276-121">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="ae276-122">次のようなコマンドを使用して、ユーザーごとのユーザーサービスポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae276-122">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="ae276-p107">新しいポリシーを作成した後、そのポリシーを、統合連絡先ストアへのアクセス権を必要とするすべてのユーザーに割り当てる必要があります。ユーザーごとのポリシーをユーザーに割り当てるには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae276-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="ae276-125">ポリシーに Lync Server が割り当てられると、ユーザーの連絡先が統合連絡先ストアに移行されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-125">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="ae276-126">移行が完了した後、ユーザーは Lync Server ではなく Exchange に保存された自分の連絡先を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ae276-126">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="ae276-127">移行が完了した時点でユーザーが Lync 2013 にログオンしている場合は、メッセージボックスが表示され、Lync からログオフするように求められ、処理を完了するために再びログオンするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae276-127">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="ae276-128">このユーザーごとのポリシーが割り当てられていないユーザーの連絡先は、統合連絡先ストアに移行されません。</span><span class="sxs-lookup"><span data-stu-id="ae276-128">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="ae276-129">これは、それらのユーザーがグローバルポリシーによって管理されており、グローバルポリシーで統合連絡先ストアの使用が無効にされているためです。</span><span class="sxs-lookup"><span data-stu-id="ae276-129">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="ae276-130">Lync Server 管理シェルで[test-csunifiedcontactstore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)コマンドレットを実行することにより、ユーザーの連絡先が統合連絡先ストアに正常に移行されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ae276-130">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ae276-131">Test-CsUnifiedContactStore が成功すれば、統合連絡先ストアへのユーザー sip:kenmyer@litwareinc.com の連絡先の移行は完了しています。</span><span class="sxs-lookup"><span data-stu-id="ae276-131">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="ae276-132">統合連絡先ストアのロールバック</span><span class="sxs-lookup"><span data-stu-id="ae276-132">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="ae276-133">ユーザーの連絡先を統合連絡先ストアから削除する必要がある場合 (たとえば、Microsoft Lync Server 2010 上でユーザーがホームポイントを設定する必要があり、そのため統合連絡先ストアを使用できなくなる場合) は、2つのことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae276-133">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="ae276-134">最初に、ユーザーに新しいユーザーサービスポリシーを割り当てて、統合連絡先ストアに連絡先を保存することを禁止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae276-134">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="ae276-135">(つまり、UcsAllowed プロパティが $False に設定されているポリシー)。このようなポリシーがない場合は、次のようなコマンドを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae276-135">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="ae276-136">その後、次のようなコマンドを使用して、この新しいユーザーごとのポリシー (NoUnifiedContactStore) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae276-136">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="ae276-137">上記のコマンドは、ユーザー Ken Myer に新しいポリシーを割り当てると共に、Ken の連絡先が統合連絡先ストアに移行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="ae276-137">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae276-p110">場合によっては、単純にユーザーの現在のユーザー サービス ポリシーを割り当て解除するだけで同じ結果が得られます。たとえば、統合連絡先ストアを有効にするユーザーごとのユーザー サービス ポリシーが Ken Myer に割り当てられているが、グローバル ポリシーでは統合連絡先ストアの使用が禁止されているとします。その場合は、Ken のユーザーごとのサービス ポリシーを割り当て解除します。それにより、Ken は自動的にグローバル ポリシーによって管理されるようになるため、統合連絡先ストアにはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae276-p110">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy. For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store. In that case, you could unassign Ken's per-user services policy. When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="ae276-142">以前に割り当てたユーザーごとのポリシーを割り当て解除するには、上記と同じコマンドを使用しますが、PolicyName パラメーターを null 値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae276-142">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="ae276-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="ae276-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="ae276-144">統合連絡先ストアを操作する際には、"Ken の連絡先が統合連絡先ストアに移行されないようにする" という点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ae276-144">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="ae276-145">単純に新しいユーザー サービス ポリシーを Ken に割り当てるだけでは、Ken の連絡先は統合連絡先ストアから移動されません。</span><span class="sxs-lookup"><span data-stu-id="ae276-145">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="ae276-146">ユーザーが Lync Server 2013 にログオンすると、システムはユーザーのユーザーサービスポリシーをチェックして、その連絡先を統合連絡先ストアに保持する必要があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae276-146">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="ae276-147">答えが「はい」である (つまり、UcsAllowed プロパティが $True に設定されている) 場合は、連絡先が統合連絡先ストアに移行されます (連絡先がまだ統合連絡先ストアに移動されていないと仮定します)。</span><span class="sxs-lookup"><span data-stu-id="ae276-147">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="ae276-148">応答が [いいえ] の場合、Lync Server は単にユーザーの連絡先を無視し、次のタスクに進みます。</span><span class="sxs-lookup"><span data-stu-id="ae276-148">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="ae276-149">つまり、Lync Server は、UcsAllowed プロパティの値に関係なく、ユーザーの連絡先を統合連絡先ストアから自動的に移動することはありません。</span><span class="sxs-lookup"><span data-stu-id="ae276-149">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="ae276-150">これはつまり、ユーザーに新しいユーザーサービスポリシーを割り当てた後に、 [invoke-csucsrollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)コマンドレットを実行して、ユーザーの連絡先を Exchange 2013 から Lync Server 2013 に移行する必要があることも意味します。</span><span class="sxs-lookup"><span data-stu-id="ae276-150">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="ae276-151">たとえば、Ken Myer に新しいユーザー サービス ポリシーを割り当てた後、次のコマンドを使用して Ken の連絡先を統合連絡先ストアから移動できます。</span><span class="sxs-lookup"><span data-stu-id="ae276-151">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="ae276-152">ユーザーサービスポリシーを変更しても、Invoke-csucsrollback コマンドレットを実行しない場合、Ken の連絡先は統合連絡先ストアから削除されません。</span><span class="sxs-lookup"><span data-stu-id="ae276-152">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="ae276-153">Invoke-csucsrollback を実行しても Ken Myer のユーザーサービスポリシーを変更しない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="ae276-153">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="ae276-154">その場合、Ken の連絡先が統合連絡先ストアから一時的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-154">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="ae276-155">この削除が一時的なものであることを念頭に置いておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="ae276-155">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="ae276-156">Ken の連絡先が統合連絡先ストアから削除された後、Lync Server 2013 は7日待機してから、Ken に割り当てられているユーザーサービスポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae276-156">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="ae276-157">統合連絡先ストアのユーザーを有効にするポリシーが Ken にまだ割り当てられている場合、その連絡先は自動的に連絡先ストアに戻されます。</span><span class="sxs-lookup"><span data-stu-id="ae276-157">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="ae276-158">統合連絡先ストアから連絡先を完全に削除するには、Invoke-csucsrollback コマンドレットを実行することに加えて、ユーザーサービスポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae276-158">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="ae276-159">移行に影響を与える可能性がある大量の変数があるため、アカウントが統合連絡先ストアに完全に移行されるまでにかかる時間を予測するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="ae276-159">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="ae276-160">ただし、一般的な規則として、少ない数の連絡先を移行する場合でも、移行が完了するまでに10分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae276-160">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

