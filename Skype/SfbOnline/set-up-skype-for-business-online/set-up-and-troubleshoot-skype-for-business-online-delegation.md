---
title: "セットアップし、トラブルシューティング Skype for Business Online の委任"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "この記事では、セットアップし、トラブルシューティング Skype for Business Online の委任する方法について説明します。この記事では、設定の推奨事項、ベスト プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。"
ms.openlocfilehash: b69f6712f78906bc955d3ce014fe8ccd6ab252c1
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="03bb0-104">セットアップし、トラブルシューティング Skype for Business Online の委任</span><span class="sxs-lookup"><span data-stu-id="03bb0-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="03bb0-p102">この記事では、セットアップし、トラブルシューティング Skype for Business Online の委任する方法について説明します。この記事では、設定の推奨事項、ベスト プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p102">This article explains how to set up and troubleshoot Skype for Business Online delegation. This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="03bb0-107">ガイドラインと要件</span><span class="sxs-lookup"><span data-stu-id="03bb0-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="03bb0-108">委任するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="03bb0-108">Guidelines for delegation</span></span>

<span data-ttu-id="03bb0-109">正常に動作する代理人の作業をセットアップするには、次のガイドラインをフォローするに依存します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="03bb0-110">使用が必要 Skype for Business 2015 フル機能の最新の更新プログラムでクライアントまたは Skype for Business 2016 の完全なクライアントです。</span><span class="sxs-lookup"><span data-stu-id="03bb0-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="03bb0-111">最新の更新プログラムで Outlook 2013 クライアントまたは Outlook 2016 クライアントを使っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="03bb0-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="03bb0-p103">代理人のコンピューターと代理人がプライマリは、1 つの Outlook メール プロファイルまたは既定のプロファイルがあることを確認します。メール プロファイルにはする必要がありますが含まれているアカウント 1 つだけにはです。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p103">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile. That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="03bb0-p104">Skype for Business の代理人と代理人は、オンラインのユーザーになります。また、必要があります両方オンラインにするか、両方の内部設置型の各アカウントの Exchange Server メールボックスします。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p104">Skype for Business for the delegator and the delegate should be Online users. Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="03bb0-116">代理人と代理人の両方に同じメジャー バージョンの Outlook を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03bb0-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="03bb0-p105">**条件を満たす**クライアント ポリシーのする**EnableExchangeDelegateSync**属性値に設定する必要があります。Skype for Business Online PowerShell モジュール**Get CSClientPolicy**コマンドレットを実行してこの設定を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p105">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy. You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="03bb0-119">代理人と代理人の両方必要がありますへのサインインが Skype for Business と Outlook 同時に別のワークステーションにします。</span><span class="sxs-lookup"><span data-stu-id="03bb0-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="03bb0-p106">共有メールボックスは Skype for Business Online の委任のサポートされていません。共有メールボックスは**sendonbehalf**アクセス制御リスト (ACL) があるないためにです。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p106">Shared mailboxes aren't supported for Skype for Business Online delegation. This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="03bb0-122">Skype for Business クライアント バージョンのサポート</span><span class="sxs-lookup"><span data-stu-id="03bb0-122">Skype for Business client version support</span></span>

||<span data-ttu-id="03bb0-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="03bb0-123">**Outlook 2013**</span></span>|<span data-ttu-id="03bb0-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="03bb0-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03bb0-125">**Lync と Skype for Business の基本的なクライアント**</span><span class="sxs-lookup"><span data-stu-id="03bb0-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="03bb0-126">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="03bb0-126">Not supported</span></span> |<span data-ttu-id="03bb0-127">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="03bb0-127">Not supported</span></span>
|<span data-ttu-id="03bb0-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="03bb0-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="03bb0-129">サポートされます</span><span class="sxs-lookup"><span data-stu-id="03bb0-129">Supported</span></span>| <span data-ttu-id="03bb0-130">サポートされます</span><span class="sxs-lookup"><span data-stu-id="03bb0-130">Supported</span></span>|
|<span data-ttu-id="03bb0-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="03bb0-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="03bb0-132">サポートされます</span><span class="sxs-lookup"><span data-stu-id="03bb0-132">Supported</span></span>| <span data-ttu-id="03bb0-133">サポートされます</span><span class="sxs-lookup"><span data-stu-id="03bb0-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="03bb0-134">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="03bb0-134">Licensing requirements</span></span>

<span data-ttu-id="03bb0-135">**Enterprise E3 ライセンス シナリオ**</span><span class="sxs-lookup"><span data-stu-id="03bb0-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="03bb0-136">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="03bb0-136">**License**</span></span>|<span data-ttu-id="03bb0-137">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="03bb0-137">**Clients**</span></span>|<span data-ttu-id="03bb0-138">**ノート**</span><span class="sxs-lookup"><span data-stu-id="03bb0-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03bb0-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="03bb0-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="03bb0-140">Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="03bb0-141">Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="03bb0-142">Skype for Business の基本的なクライアントでは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="03bb0-143">Mac クライアントでは、通話、会議ではなくを委任することができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="03bb0-144">Office 365 の電話システムと Office 365 xCalling プランと Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="03bb0-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="03bb0-145">Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="03bb0-146">Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="03bb0-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="03bb0-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="03bb0-148">Skype for Business の基本的なクライアントでは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="03bb0-149">Mac クライアントでは、通話、会議ではなくを委任することができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="03bb0-150">**エンタープライズ E5 ライセンス シナリオ**</span><span class="sxs-lookup"><span data-stu-id="03bb0-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="03bb0-151">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="03bb0-151">**License**</span></span>|<span data-ttu-id="03bb0-152">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="03bb0-152">**Clients**</span></span>|<span data-ttu-id="03bb0-153">**ノート**</span><span class="sxs-lookup"><span data-stu-id="03bb0-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03bb0-154">エンタープライズ E5</span><span class="sxs-lookup"><span data-stu-id="03bb0-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="03bb0-155">Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="03bb0-156">Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="03bb0-157">Skype for Business の基本的なクライアントでは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="03bb0-158">Mac クライアントでは、通話、会議ではなくを委任することができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="03bb0-159">エンタープライズ E5 と Office 365 の通話プラン</span><span class="sxs-lookup"><span data-stu-id="03bb0-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="03bb0-160">Skype for Business for Mac 2016</span><span class="sxs-lookup"><span data-stu-id="03bb0-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="03bb0-161">Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="03bb0-162">Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用</span><span class="sxs-lookup"><span data-stu-id="03bb0-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="03bb0-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="03bb0-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="03bb0-164">Skype for Business の基本的なクライアントでは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="03bb0-165">Mac クライアントでは、通話、会議ではなくを委任することができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="03bb0-166">セットアップして、呼び出しを確認します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-166">Set up and verify delegation</span></span>

<span data-ttu-id="03bb0-167">Skype for Business Online の委任をセットアップするには、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="03bb0-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="03bb0-168">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="03bb0-168">For Windows clients</span></span>

 <span data-ttu-id="03bb0-169">**着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="03bb0-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="03bb0-170">**ツール**を選択する > **オプション** > **着信の転送設定**します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="03bb0-171">**代理人メンバーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="03bb0-172">**追加**] を選択、代理人を追加するを選択し、[ **ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03bb0-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="03bb0-173">**着信の転送タブが表示されません。**</span><span class="sxs-lookup"><span data-stu-id="03bb0-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="03bb0-174">Outlook では、**ファイル**の選択 > **アカウント設定** > **代理人アクセス** > **追加**します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="03bb0-175">見つけてを代理人を務める人の名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="03bb0-176">[**予定表**] メニューを選択し、選択**エディター (読み取り、作成、およびアイテムの変更)**します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="03bb0-177">Mac クライアント - Lync</span><span class="sxs-lookup"><span data-stu-id="03bb0-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="03bb0-178">**着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="03bb0-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="03bb0-p107">クライアントは、[**代理人メンバーの編集**] リンクを含む**着信の転送**] タブがない場合は、代理人が Mac コンピューター上にある代理人必要がありますサインインを Windows ベースのコンピューターに委任を設定するためにします。Mac クライアントできない MAPI 接続を行い、これは、Outlook からビジネス委任の Skype を確立する必要があるためにです。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p107">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation. This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="03bb0-181">成功を確認します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-181">Verify success</span></span>

<span data-ttu-id="03bb0-p108">代理人が**< 名 > の代理人として追加された場合**の表示セットアップが失敗した場合は、メッセージとも**通話を管理する連絡先が**グループを作成します。代理人の**代理人**グループを作成することが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p108">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created. The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03bb0-p109">委任の権限は、通常のセットアップ プロセスの 30 分以内で表示されます。ただし、完了するまで 24 時間かかることができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p109">Delegation permissions usually appear within 30 minutes of the setup process. However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="03bb0-186">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="03bb0-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="03bb0-187">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="03bb0-187">Common issues</span></span>

- > <span data-ttu-id="03bb0-188">**1 の問題**代理人のエントリは、代理人が Outlook クライアントから代理人を削除した後に**通話を管理する連絡先が**グループの表示を続けます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="03bb0-189">**解決方法 1**Skype for Business クライアントでは、**代理人**] で、代理人を右クリックし、[**グループから削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="03bb0-190">**2 の問題**Outlook クライアントを代理人アクセスを許可した後、確認メッセージも、**通話を管理する連絡先が**グループを代理人が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="03bb0-191">**解決方法 2**Outlook クライアントから委任を削除する、レプリケーションは、15 分待ってからもう一度、代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="03bb0-192">その他の一般的な問題</span><span class="sxs-lookup"><span data-stu-id="03bb0-192">Other common issues</span></span>

- <span data-ttu-id="03bb0-193">25 委任者と 25 の代理人のしきい値を超えた場合は、委任が機能しません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="03bb0-194">Skype for Business の基本的なクライアントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03bb0-195">Skype for Business の基本的なクライアントをインストールしている場合、削除し、呼び出しを解除します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="03bb0-196">**MAPI 状態**の値には、 **[ok]**がない場合は場合、は、 **SIP**および**SMTP**値と一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03bb0-197">MAPI 状態 Business と Outlook の Skype を初めて起動した後は、 **[ok]**として表示するのには数分かかることができます。</span><span class="sxs-lookup"><span data-stu-id="03bb0-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="03bb0-198">セキュリティ グループを作成して、セキュリティ グループの代理人のアクセス許可の追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="03bb0-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="03bb0-p110">MAPI では使用できません。[Skype for Business 2016 クライアントでの"MAPI は利用できません"エラー](https://support.microsoft.com/en-us/help/3147130)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p110">MAPI is unavailable. See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="03bb0-p111">Exchange Online メールボックスに Skype for Business クライアントからアクセスできません。この問題が発生した場合は、要件を満たす必要かどうかを確認する[Outlook 接続のテスト](https://testconnectivity.microsoft.com/)を実行します。</span><span class="sxs-lookup"><span data-stu-id="03bb0-p111">The Exchange Online mailbox isn't accessible through the Skype for Business client. If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="03bb0-203">関連トピック</span><span class="sxs-lookup"><span data-stu-id="03bb0-203">Related topics</span></span>
[<span data-ttu-id="03bb0-204">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="03bb0-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="03bb0-205">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="03bb0-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
