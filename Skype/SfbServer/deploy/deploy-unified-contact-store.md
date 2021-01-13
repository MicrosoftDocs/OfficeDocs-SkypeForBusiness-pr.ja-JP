---
title: 'Skype for Business Server での統合連絡先ストアの展開 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '概要: Skype for Business Server で統合連絡先ストアを有効にします。'
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812557"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="e3e09-103">Skype for Business Server での統合連絡先ストアの展開</span><span class="sxs-lookup"><span data-stu-id="e3e09-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="e3e09-104">**概要:** Skype for Business Server で統合連絡先ストアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3e09-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="e3e09-105">Skype for Business Server で統合連絡先ストアを有効にする場合、トポロジ設定は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="e3e09-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="e3e09-106">ユーザーの統合連絡先ストアを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="e3e09-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="e3e09-107">統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="e3e09-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="e3e09-108">ユーザーは少なくとも 1 回は Skype for Business でログインします。</span><span class="sxs-lookup"><span data-stu-id="e3e09-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="e3e09-109">ユーザーの連絡先が移行された後、ユーザーは Skype for Business にログインすると自動的に行われます。ユーザーは、Skype for Business、Outlook 2013、または Outlook Web Access から Skype for Business の連絡先にアクセスして管理できます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="e3e09-110">ユーザーは、Outlook または Outlook Web Access から連絡先を管理するために Skype for Business にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e09-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e3e09-111">移行後にユーザーが Skype for Business からログインした場合、連絡先とグループは使用可能で最新の情報に更新されますが、ユーザーはそれらの連絡先を管理 (追加、削除、移動、タグ付け、タグ解除、または変更) できません。</span><span class="sxs-lookup"><span data-stu-id="e3e09-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="e3e09-112">統合連絡先ストアでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="e3e09-112">Enable users for unified contact store</span></span>

<span data-ttu-id="e3e09-113">Skype for Business Server を展開してトポロジを公開すると、統合連絡先ストアは既定ですべてのユーザーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="e3e09-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="e3e09-114">Skype for Business Server の展開後に統合連絡先ストアを有効にする追加のアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3e09-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="e3e09-115">ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="e3e09-116">この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="e3e09-117">統合連絡先ストアでユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="e3e09-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="e3e09-118">Skype for Business Server 管理シェルを起動します **。[スタート**] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3e09-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e3e09-119">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e3e09-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="e3e09-120">すべての Skype for Business Server ユーザーに対して統合連絡先ストアをグローバルに有効にするには、コマンド ライン インターフェイスの Windows PowerShellコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="e3e09-121">特定のサイトのユーザーに対して統合連絡先ストアを有効にするには、プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="e3e09-122">例:</span><span class="sxs-lookup"><span data-stu-id="e3e09-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="e3e09-123">テナント別に統合連絡先ストアを有効にするには、プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="e3e09-124">例:</span><span class="sxs-lookup"><span data-stu-id="e3e09-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="e3e09-125">特定のユーザーに対して統合連絡先ストアを有効にするには、プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="e3e09-126">ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="e3e09-127">例:</span><span class="sxs-lookup"><span data-stu-id="e3e09-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="e3e09-128">前の例では、最初のコマンドで UcsAllowed フラグが True に設定された UCS Enabled Users という名前の新しいユーザーごとのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="e3e09-129">2 番目のコマンドは、Ken Myer という表示名を持つユーザーにポリシーを割り当て、Ken Myer が統合連絡先ストアに対して有効になっているという意味です。</span><span class="sxs-lookup"><span data-stu-id="e3e09-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="e3e09-130">統合連絡先ストアへのユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="e3e09-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="e3e09-131">次の場合、ユーザーの連絡先は Exchange 2013 サーバーに自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="e3e09-132">UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="e3e09-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="e3e09-133">Exchange 2013 メールボックスでプロビジョニングされ、少なくとも 1 回はメールボックスにサインインしています。</span><span class="sxs-lookup"><span data-stu-id="e3e09-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="e3e09-134">ユーザーが Skype for Business リッチ クライアントを使用してログインした場合。</span><span class="sxs-lookup"><span data-stu-id="e3e09-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="e3e09-135">ユーザーが Lync 以前のクライアントでログインした場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーのサービス ポリシーは無視され、ユーザーの連絡先は Skype for Business Server に残ります。</span><span class="sxs-lookup"><span data-stu-id="e3e09-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="e3e09-136">ユーザーの連絡先が移行されているかどうかは、次のどちらかの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="e3e09-137">クライアント コンピューターで次のレジストリ キーを調べます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="e3e09-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL \> \UCS</span><span class="sxs-lookup"><span data-stu-id="e3e09-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="e3e09-139">ユーザーの連絡先が Exchange 2013 に保存されている場合、このキーには、値 2165 の InUCSMode の値が含まれる。</span><span class="sxs-lookup"><span data-stu-id="e3e09-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="e3e09-140">**Test-CsUnifiedContactStore** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="e3e09-141">Skype for Business Server 管理シェル コマンド ラインで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="e3e09-142">**Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。</span><span class="sxs-lookup"><span data-stu-id="e3e09-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="e3e09-143">移行したユーザーをロールバックする</span><span class="sxs-lookup"><span data-stu-id="e3e09-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="e3e09-144">統合連絡先ストア機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ、連絡先をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="e3e09-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e3e09-145">ロールバックするには、ユーザーのポリシーを無効にし **、Invoke-CsUcsRollback コマンドレットを実行** します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e3e09-146">**Invoke-CsUcsRollback** を単独で実行するだけでは、永続的なロールバックを保証するには十分ではありません。ポリシーが無効にされていない場合は、統合連絡先ストアの移行が再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e3e09-147">たとえば、Exchange 2013 が Exchange 2010 にロールバックされ、そのユーザーのメールボックスが Exchange 2013 に移動されたため、ユーザーがロールバックされた場合、統合連絡先ストアの移行はロールバックの 7 日後に再び開始されます。ユーザー サービス ポリシーで統合連絡先ストアがユーザーに対して有効な場合です。</span><span class="sxs-lookup"><span data-stu-id="e3e09-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="e3e09-148">**Move-CsUser コマンドレット** は、次の状況で、ユーザーの連絡先ストアを Exchange 2013 から Skype for Business Server に自動的にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="e3e09-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="e3e09-149">ユーザーが Skype for Business Server から Microsoft Lync Server 2013 または Lync Server 2010 に移動される場合。</span><span class="sxs-lookup"><span data-stu-id="e3e09-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="e3e09-150">ユーザーが Skype for Business Online からオンプレミスの Skype for Business Server に、またはその逆に移動された場合など、ユーザーがクロスオンプレミスに移行される場合。</span><span class="sxs-lookup"><span data-stu-id="e3e09-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="e3e09-p107">バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="e3e09-153">ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートし、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="e3e09-154">ユーザーを Exchange 2013 に移行した後にユーザー データをエクスポートする場合は、移行をロールバックし、移行後に何らかの理由でデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。</span><span class="sxs-lookup"><span data-stu-id="e3e09-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e3e09-155">Exchange メールボックスを Exchange 2013 から Exchange 2010 に移動する前に、Exchange 管理者は、Skype for Business Server 管理者が最初に Skype for Business Server のユーザー連絡先を Exchange 2013 から Skype for Business Server にロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e09-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="e3e09-156">統合連絡先ストアの連絡先を Skype for Business Server にロールバックするには、このセクションの後半の「統合連絡先ストアの連絡先を Exchange 2013 から Skype for Business Server にロールバックするには」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e09-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="e3e09-157">**ユーザーの連絡先をロールバックする方法:\*\*\*\*Move-CsUser** コマンドレットを使用して Skype for Business Server 2015 と Lync Server 2010 の間でユーザーを移動する場合 **、Move-CsUser** コマンドレットは、Skype for Business Server 2015 から Lync Server 2010 にユーザーを移動するときに統合連絡先ストアを自動的にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="e3e09-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="e3e09-158">**Move-CsUser** は統合連絡先ストア ポリシーを無効にしないので、ユーザーが Skype for Business Server 2015 に戻された場合、統合連絡先ストアへの移行が再び実行されます。</span><span class="sxs-lookup"><span data-stu-id="e3e09-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

