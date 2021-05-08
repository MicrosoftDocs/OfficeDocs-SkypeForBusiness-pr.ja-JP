---
title: Skype for Business Online の代理のセットアップとトラブルシューティング
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: この記事では、オンライン委任の設定とトラブルシューティングSkype for Business説明します。 この記事では、セットアップの推奨事項、ベスト プラクティス、およびトラブルシューティングの手順のガイダンスを提供します。
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239826"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="7d8ef-104">Skype for Business Online の代理のセットアップとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7d8ef-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="7d8ef-105">この記事では、オンライン委任の設定とトラブルシューティングSkype for Business説明します。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="7d8ef-106">この記事では、セットアップの推奨事項、ベスト プラクティス、およびトラブルシューティングの手順のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="7d8ef-107">ガイドラインと要件</span><span class="sxs-lookup"><span data-stu-id="7d8ef-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="7d8ef-108">委任のガイドライン</span><span class="sxs-lookup"><span data-stu-id="7d8ef-108">Guidelines for delegation</span></span>

<span data-ttu-id="7d8ef-109">委任を正しく機能するように設定および取得するには、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="7d8ef-110">最新の更新プログラムまたは Skype for Business 201 Skype for Business 6 フル クライアントで Skype for Business 2015 フル クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="7d8ef-111">最新の更新プログラムまたはOutlook 2013 クライアントを使用Outlook 2016があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="7d8ef-112">委任者と代理人のコンピューターに、プライマリ プロファイルOutlook既定のプロファイルであるメール プロファイルが 1 つ含め込み、</span><span class="sxs-lookup"><span data-stu-id="7d8ef-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="7d8ef-113">そのメール プロファイルには、1 つのアカウントのみを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="7d8ef-114">Skype for Business代理人のユーザーはオンライン ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="7d8ef-115">また、各Exchange Serverのメールボックスは、両方ともオンラインか、両方がオンプレミスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="7d8ef-116">委任者と代理人の両方が、同じメジャー バージョンのアカウントを使用Outlook。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="7d8ef-117">クライアント **ポリシーで EnableExchangeDelegateSync** 属性値を **true** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="7d8ef-118">この設定を確認するには、オンライン PowerShell モジュールの Skype for Business **Get-CSClientPolicy** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="7d8ef-119">委任者と代理人の両方が、Skype for Businessにサインインし、Outlookワークステーションで同時にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="7d8ef-120">共有メールボックスは、オンライン委任のSkype for Businessサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="7d8ef-121">これは、共有メールボックスに **sendonbehalf** アクセス制御リスト (ACL) が含まれるためです。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="7d8ef-122">Skype for Business クライアント バージョンのサポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-122">Skype for Business client version support</span></span>

||<span data-ttu-id="7d8ef-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-123">**Outlook 2013**</span></span>|<span data-ttu-id="7d8ef-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d8ef-125">**Lync/Skype for Business Basic クライアント**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="7d8ef-126">非サポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-126">Not supported</span></span> |<span data-ttu-id="7d8ef-127">非サポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-127">Not supported</span></span>
|<span data-ttu-id="7d8ef-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="7d8ef-129">サポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-129">Supported</span></span>| <span data-ttu-id="7d8ef-130">サポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-130">Supported</span></span>|
|<span data-ttu-id="7d8ef-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="7d8ef-132">サポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-132">Supported</span></span>| <span data-ttu-id="7d8ef-133">サポート</span><span class="sxs-lookup"><span data-stu-id="7d8ef-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="7d8ef-134">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="7d8ef-134">Licensing requirements</span></span>

<span data-ttu-id="7d8ef-135">**EnterpriseE3 ライセンスシナリオ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="7d8ef-136">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-136">**License**</span></span>|<span data-ttu-id="7d8ef-137">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-137">**Clients**</span></span>|<span data-ttu-id="7d8ef-138">**メモ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d8ef-139">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="7d8ef-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="7d8ef-140">2013 または Skype for Business で使用される Lync 2013 (Outlook 2015) Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7d8ef-141">Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="7d8ef-142">Skype for BusinessBasic クライアントでは委任はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7d8ef-143">Mac クライアントの場合、通話を委任できますが、会議は委任されません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="7d8ef-144">EnterpriseE3 と Office 365 電話システム + Office 365 xCalling プラン</span><span class="sxs-lookup"><span data-stu-id="7d8ef-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="7d8ef-145">2013 または Skype for Business で使用される Lync 2013 (Outlook 2015) Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7d8ef-146">Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7d8ef-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="7d8ef-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="7d8ef-148">Skype for BusinessBasic クライアントでは委任はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7d8ef-149">Mac クライアントの場合、通話を委任できますが、会議は委任されません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="7d8ef-150">**EnterpriseE5 ライセンスシナリオ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="7d8ef-151">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-151">**License**</span></span>|<span data-ttu-id="7d8ef-152">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-152">**Clients**</span></span>|<span data-ttu-id="7d8ef-153">**メモ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d8ef-154">EnterpriseE5</span><span class="sxs-lookup"><span data-stu-id="7d8ef-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="7d8ef-155">Outlook 2013 または Outlook 2016 で使用される Lync 2013 (Skype for Business 2015)。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="7d8ef-156">Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="7d8ef-157">Skype for BusinessBasic クライアントでは委任はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7d8ef-158">Mac クライアントの場合、通話を委任できますが、会議は委任されません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="7d8ef-159">EnterpriseE5 + Office 365通話プラン</span><span class="sxs-lookup"><span data-stu-id="7d8ef-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="7d8ef-160">Skype for Business for Mac 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="7d8ef-161">2013 または Skype for Business で使用される Lync 2013 (Outlook 2015) Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7d8ef-162">Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d8ef-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7d8ef-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="7d8ef-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="7d8ef-164">Skype for BusinessBasic クライアントでは委任はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7d8ef-165">Mac クライアントの場合、通話を委任できますが、会議は委任されません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="7d8ef-166">委任を設定して確認する</span><span class="sxs-lookup"><span data-stu-id="7d8ef-166">Set up and verify delegation</span></span>

<span data-ttu-id="7d8ef-167">オンライン委任をSkype for Businessするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="7d8ef-168">Windows クライアントの場合</span><span class="sxs-lookup"><span data-stu-id="7d8ef-168">For Windows clients</span></span>

 <span data-ttu-id="7d8ef-169">**[通話の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="7d8ef-170">[ツール **] [**  >  **オプション]**  >  **[通話の転送] 設定。**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="7d8ef-171">[代理人 **メンバーの編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="7d8ef-172">[ **追加]** を選択し、追加する代理人を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="7d8ef-173">**[通話の転送なし] タブ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="7d8ef-174">[Outlook で、[ファイル アカウント]**を**  >  **選択し、[代理人設定**  >  **追加] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="7d8ef-175">代理人になるユーザーの名前を見つけて追加します。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="7d8ef-176">[予定表] **メニューを** 選択し、[エディター] (アイテムの読み取り、作成、変更が **可能) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="7d8ef-177">Mac クライアントの場合 - Lync</span><span class="sxs-lookup"><span data-stu-id="7d8ef-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="7d8ef-178">**[通話の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="7d8ef-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="7d8ef-179">クライアントに [代理人メンバーの編集] リンクがある [通話の転送] タブが表示され、委任者が Mac コンピューター上にある場合、委任を設定するには、委任者が Windows ベースのコンピューターにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="7d8ef-180">これは、Mac クライアントが MAPI 接続を確立できないためであり、これは、ユーザーからの委任を確立Skype for Business要件Outlook。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="7d8ef-181">成功を確認する</span><span class="sxs-lookup"><span data-stu-id="7d8ef-181">Verify success</span></span>

<span data-ttu-id="7d8ef-182">セットアップが成功すると、代理人に **[< Name>** の代理人として追加されました] というメッセージが表示され、[通話を管理するユーザー  ] グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="7d8ef-183">委任者は、[代理人] グループ **が作成された** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7d8ef-184">委任アクセス許可は、通常、セットアップ プロセスから 30 分以内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="7d8ef-185">ただし、このプロセスが完了するには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="7d8ef-186">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7d8ef-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="7d8ef-187">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="7d8ef-187">Common issues</span></span>

- > <span data-ttu-id="7d8ef-188">**問題 1** 代理人エントリは、委任者が代理人をクライアントから削除した後も、[通話の管理を行うユーザー] グループOutlookされます。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="7d8ef-189">**解決策 1** 新しいSkype for Businessで、[代理人] グループの代理人を右クリックし、[グループから削除]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="7d8ef-190">**問題 2** Outlook クライアントを通じて代理人アクセスが許可された後、代理人の確認メッセージも [通話の管理するユーザー] グループも表示されません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="7d8ef-191">**解決策 2** 委任をクライアントから削除Outlook約 15 分待ち、もう一度代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="7d8ef-192">その他の一般的な問題</span><span class="sxs-lookup"><span data-stu-id="7d8ef-192">Other common issues</span></span>

- <span data-ttu-id="7d8ef-193">委任は、25 人の委任者と 25 人の代理人のしきい値を超えた場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="7d8ef-194">Basic Skype for Businessはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7d8ef-195">Skype for Business Basic クライアントをインストールすると、委任が削除され、破損します。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="7d8ef-196">MAPI 状態 **の値が** OK ではない場合 **は、SIP** と SMTP の値が一致 **する必要** があります。 </span><span class="sxs-lookup"><span data-stu-id="7d8ef-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7d8ef-197">MAPI の状態が[OK] と表示されるのは、最初に開始した後に **[OK]** Skype for Business数分Outlook。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="7d8ef-198">セキュリティ グループの作成と、そのセキュリティ グループの委任アクセス許可の追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="7d8ef-199">MAPI は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-199">MAPI is unavailable.</span></span> <span data-ttu-id="7d8ef-200">[2016 年 2016 年のクライアントで「MAPI を使用できない」Skype for Businessを参照してください](https://support.microsoft.com/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="7d8ef-201">メールボックスExchange OnlineクライアントからアクセスSkype for Businessできません。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="7d8ef-202">この場合は、接続テストOutlook[を実行して](https://testconnectivity.microsoft.com/)、接続テストに合格した必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ef-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7d8ef-203">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7d8ef-203">Related topics</span></span>
[<span data-ttu-id="7d8ef-204">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="7d8ef-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7d8ef-205">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="7d8ef-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
