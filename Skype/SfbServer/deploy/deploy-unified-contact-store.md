---
title: 'ビジネス サーバーの Skype での統合連絡先ストアを展開します。 '
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '概要: は、Skype のビジネス サーバーの統合連絡先ストアを有効にします。'
ms.openlocfilehash: 36515e9542a18d422254292b0cf2a2b4ef937178
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978222"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="d1994-103">ビジネス サーバーの Skype での統合連絡先ストアを展開します。</span><span class="sxs-lookup"><span data-stu-id="d1994-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="d1994-104">**の概要:** Skype のビジネス サーバーの統合連絡先ストアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d1994-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="d1994-105">ビジネス サーバーの Skype での統合連絡先ストアを有効にするとしても、任意のトポロジ設定は不要です。</span><span class="sxs-lookup"><span data-stu-id="d1994-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="d1994-106">ユーザーに対して統合連絡先ストアを有効にするには、次の条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1994-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="d1994-107">統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="d1994-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="d1994-108">ユーザーのログオン ビジネス用の Skype で少なくとも 1 回。</span><span class="sxs-lookup"><span data-stu-id="d1994-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="d1994-109">ユーザーの連絡先を移行した後、ビジネスの Skype を使用してユーザーのログオン時に自動的に行われますユーザーはアクセスし、ビジネス、2013 年 Outlook または Outlook Web Access の Skype からビジネス用連絡先に、Skype を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d1994-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="d1994-110">ユーザーは、Outlook または Outlook Web Access からこれらの連絡先を管理するためにビジネス用の Skype にログインするのにはありません。</span><span class="sxs-lookup"><span data-stu-id="d1994-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1994-111">ユーザーのログオン ビジネス用の Skype からの移行後、利用可能で、最新の状態は、連絡先およびグループが、ユーザー (つまり、追加、削除、移動、タグ、タグ、または変更) を管理することはできませんそれらの連絡先です。</span><span class="sxs-lookup"><span data-stu-id="d1994-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="d1994-112">統合連絡先ストアのユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="d1994-112">Enable users for unified contact store</span></span>

<span data-ttu-id="d1994-113">Skype をビジネスのサーバーの展開トポロジを公開すると、統合連絡先ストアはすべてのユーザーに対して既定で有効。 にします。</span><span class="sxs-lookup"><span data-stu-id="d1994-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="d1994-114">Skype ビジネス サーバーの展開後は、統合連絡先ストアを有効にする追加アクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d1994-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="d1994-115">ただし、ユーザーは統合連絡先ストアの使用をカスタマイズするのには、**セット CsUserServicesPolicy**コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1994-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="d1994-116">この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d1994-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="d1994-117">統合連絡先ストアでユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d1994-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="d1994-118">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスの Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="d1994-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d1994-119">次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1994-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="d1994-120">ビジネス サーバーのユーザーのすべての Skype のグローバルの統合連絡先ストアを有効にするには、Windows PowerShell のコマンド ライン インターフェイスで次のコマンドレットを間します。</span><span class="sxs-lookup"><span data-stu-id="d1994-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="d1994-121">統合連絡先ストアを特定のサイトのユーザーに対して有効にするには、プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d1994-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="d1994-122">例:</span><span class="sxs-lookup"><span data-stu-id="d1994-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="d1994-123">統合連絡先ストアをテナントごとに有効にするには、プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d1994-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="d1994-124">例:</span><span class="sxs-lookup"><span data-stu-id="d1994-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="d1994-125">統合連絡先ストアを特定のユーザーに対して有効にするには、プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d1994-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="d1994-126">ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1994-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="d1994-127">例:</span><span class="sxs-lookup"><span data-stu-id="d1994-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="d1994-p104">前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを UCS Enabled Users という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d1994-p104">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="d1994-130">統合連絡先ストアへのユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="d1994-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="d1994-131">ユーザーの連絡先は、Exchange 2013 サーバーに自動的に移行するとき、ユーザー。</span><span class="sxs-lookup"><span data-stu-id="d1994-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="d1994-132">UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="d1994-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="d1994-133">Exchange 2013 メールボックスに準備されているしにサインインして、メールボックスに少なくとも 1 回。</span><span class="sxs-lookup"><span data-stu-id="d1994-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="d1994-134">リッチ クライアントのビジネスを Skype を使用してにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d1994-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="d1994-135">Lync または以前のクライアントを使用して、ユーザーがログオンした場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合は、ユーザー サービス ポリシーは無視され、ユーザーの連絡先に保存しておく Skype ビジネス サーバー。</span><span class="sxs-lookup"><span data-stu-id="d1994-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="d1994-136">ユーザーの連絡先が移行されているかどうかは、次のいずれかの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1994-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="d1994-137">クライアント コンピューターで次のレジストリ キーを調べます。</span><span class="sxs-lookup"><span data-stu-id="d1994-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="d1994-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="d1994-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="d1994-139">Exchange 2013 では、ユーザーの連絡先が保存されている場合、このキーには、2165 の値を持つには、InUCSMode の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1994-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="d1994-140">**テスト CsUnifiedContactStore**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1994-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="d1994-141">ビジネス サーバー管理シェル コマンド ラインの Skype で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d1994-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="d1994-142">**CsUnifiedContactStore のテスト**が成功すると、ユーザーの連絡先は、統合連絡先ストアに移行されました。</span><span class="sxs-lookup"><span data-stu-id="d1994-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="d1994-143">移行したユーザーのロールバック</span><span class="sxs-lookup"><span data-stu-id="d1994-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="d1994-144">ロールバックする必要がある場合は、統合連絡先ストアの機能を元に戻す、連絡先、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ。</span><span class="sxs-lookup"><span data-stu-id="d1994-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="d1994-145">ロールバックし、ユーザーのポリシーを無効にする**呼び出し CsUcsRollback**コマンドレットを実行し、します。</span><span class="sxs-lookup"><span data-stu-id="d1994-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="d1994-146">**呼び出し CsUcsRollback**だけを実行するだけではありません、永続的なロールバックを確認するのに十分な統合連絡先ストアの移行が再び開始されるポリシーが無効になっていない場合。</span><span class="sxs-lookup"><span data-stu-id="d1994-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="d1994-147">などの場合は、ユーザーがいるために、ロールバック Exchange 2010 を Exchange 2013 がロールバックされ、ユーザーのメールボックスを Exchange 2013 に移動し、統合連絡先ストアの移行が開始される、ロールバックした後、再び 7 日間統一された取引先担当者を保存する場合に限りユーザー サービス ポリシーでユーザーにも有効です。</span><span class="sxs-lookup"><span data-stu-id="d1994-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="d1994-148">**移動 CsUser**コマンドレットを自動的にロールバック連絡先ストアのユーザーの Exchange 2013 から Skype をビジネス サーバーの次のような場合。</span><span class="sxs-lookup"><span data-stu-id="d1994-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="d1994-149">ユーザーを移動するとき Skype からビジネスのサーバーに Microsoft Lync Server 2013 または Lync Server 2010 にします。</span><span class="sxs-lookup"><span data-stu-id="d1994-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="d1994-150">設置型の場合は、ユーザーを移動するとき Skype のオンライン ビジネスの Skype をビジネス サーバー設置型など、相互のユーザーを移行するとき、またはその逆。</span><span class="sxs-lookup"><span data-stu-id="d1994-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="d1994-p107">バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="d1994-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="d1994-153">ユーザーの連絡先は、Exchange 2013 に移行し、次に、移行後、同じデータをインポートする前に、連絡先リストをエクスポートする場合は、統合連絡先ストアのデータと連絡先の一覧が破損します。</span><span class="sxs-lookup"><span data-stu-id="d1994-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="d1994-154">Exchange 2013 にユーザーを移行した後にユーザーのデータをエクスポートする場合、移行をロールバックし、何らかの理由は、移行後のデータをインポートする、統合された連絡先データを格納および連絡先リストが破損しています。</span><span class="sxs-lookup"><span data-stu-id="d1994-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d1994-155">Exchange 2010 を Exchange 2013 から Exchange メールボックスを移動する前に Exchange 管理者は必ず、ビジネス サーバー管理者の Skype 最初ロール ・ バックされたビジネス サーバー ユーザーの連絡先を Skype Exchange 2013 の Skype にビジネス サーバーです。</span><span class="sxs-lookup"><span data-stu-id="d1994-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="d1994-156">統合連絡先ストアの連絡先にロールバック Skype ビジネス サーバーに対して、手順を参照して統合連絡先ストアの連絡先を Exchange 2013 に Skype for ビジネス サーバーからロールバック"するには」後でこのセクションで。</span><span class="sxs-lookup"><span data-stu-id="d1994-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="d1994-157">**ユーザーの連絡先をロールバックする方法:****移動 CsUser**コマンドレットが自動的にロールバック統合連絡先ストアの Skype からユーザーを移動するため、これらの手順をスキップできますビジネス サーバー 2015 の Skype と Lync Server 2010 のユーザーを移動する**移動 CsUser**コマンドレットを使用する場合Lync Server 2010 サーバー 2015 ビジネスです。</span><span class="sxs-lookup"><span data-stu-id="d1994-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="d1994-158">**Csuser からの移動**は無効に統合連絡先ストア ポリシー、ユーザーに戻して Skype ビジネス サーバー 2015 の場合、統合連絡先ストアへの移行が繰り返されるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1994-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

