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
description: この記事では、Skype for Business Online の委任のセットアップとトラブルシューティングの方法について説明します。 この記事では、セットアップの推奨事項、ベストプラクティス、およびトラブルシューティングの手順に関するガイダンスを示します。
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706482"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="d866d-104">Skype for Business Online の代理のセットアップとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d866d-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="d866d-105">この記事では、Skype for Business Online の委任のセットアップとトラブルシューティングの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d866d-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="d866d-106">この記事では、セットアップの推奨事項、ベストプラクティス、およびトラブルシューティングの手順に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="d866d-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="d866d-107">ガイドラインと要件</span><span class="sxs-lookup"><span data-stu-id="d866d-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="d866d-108">代理人のためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="d866d-108">Guidelines for delegation</span></span>

<span data-ttu-id="d866d-109">委任を正しく動作させるための設定と取得は、次のガイドラインに従うことによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d866d-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="d866d-110">最新の更新プログラムまたは Skype for Business 2016 フルクライアントを使用して、Skype for Business 2015 フルクライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="d866d-111">最新の更新プログラムまたは Outlook 2016 クライアントで Outlook 2013 クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="d866d-112">委任者および代理人のコンピューターに、プライマリまたは既定のプロファイルである Outlook メールプロファイルが1つ含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d866d-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="d866d-113">このメールプロファイルには、アカウントが1つだけ含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="d866d-114">Skype for Business for 委任者と代理人は、オンラインユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="d866d-115">また、各アカウントの Exchange Server メールボックスは、両方ともオンラインであるか、両方ともオンプレミスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="d866d-116">委任者と代理人の両方が、同じメジャーバージョンの Outlook を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="d866d-117">クライアントポリシーで**EnableExchangeDelegateSync**属性値が**true**に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="d866d-118">この設定を確認するには、Skype for Business Online PowerShell モジュールで、 **CSClientPolicy**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d866d-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="d866d-119">委任者と代理人の両方が、異なるワークステーションで Skype for Business と Outlook を同時にサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="d866d-120">共有メールボックスは、Skype for Business Online の委任ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="d866d-121">これは、共有メールボックスに**sendonbehalf**アクセス制御リスト (ACL) が含まれていないためです。</span><span class="sxs-lookup"><span data-stu-id="d866d-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="d866d-122">Skype for Business クライアントのバージョンのサポート</span><span class="sxs-lookup"><span data-stu-id="d866d-122">Skype for Business client version support</span></span>

||<span data-ttu-id="d866d-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="d866d-123">**Outlook 2013**</span></span>|<span data-ttu-id="d866d-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="d866d-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d866d-125">**Lync/Skype for Business Basic クライアント**</span><span class="sxs-lookup"><span data-stu-id="d866d-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="d866d-126">非サポート</span><span class="sxs-lookup"><span data-stu-id="d866d-126">Not supported</span></span> |<span data-ttu-id="d866d-127">非サポート</span><span class="sxs-lookup"><span data-stu-id="d866d-127">Not supported</span></span>
|<span data-ttu-id="d866d-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="d866d-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="d866d-129">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d866d-129">Supported</span></span>| <span data-ttu-id="d866d-130">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d866d-130">Supported</span></span>|
|<span data-ttu-id="d866d-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="d866d-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="d866d-132">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d866d-132">Supported</span></span>| <span data-ttu-id="d866d-133">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d866d-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="d866d-134">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="d866d-134">Licensing requirements</span></span>

<span data-ttu-id="d866d-135">**Enterprise E3 ライセンスのシナリオ**</span><span class="sxs-lookup"><span data-stu-id="d866d-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="d866d-136">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="d866d-136">**License**</span></span>|<span data-ttu-id="d866d-137">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="d866d-137">**Clients**</span></span>|<span data-ttu-id="d866d-138">**メモ**</span><span class="sxs-lookup"><span data-stu-id="d866d-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d866d-139">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="d866d-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="d866d-140">Outlook 2013 または Outlook 2016 で使用されている Lync 2013 (Skype for Business 2015)</span><span class="sxs-lookup"><span data-stu-id="d866d-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d866d-141">Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="d866d-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="d866d-142">Skype for Business Basic クライアントは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d866d-143">Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。</span><span class="sxs-lookup"><span data-stu-id="d866d-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="d866d-144">Enterprise E3 と Office 365 電話システム + Office 365 xCalling プラン</span><span class="sxs-lookup"><span data-stu-id="d866d-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="d866d-145">Outlook 2013 または Outlook 2016 で使用されている Lync 2013 (Skype for Business 2015)</span><span class="sxs-lookup"><span data-stu-id="d866d-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d866d-146">Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="d866d-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d866d-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d866d-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="d866d-148">Skype for Business Basic クライアントは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d866d-149">Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。</span><span class="sxs-lookup"><span data-stu-id="d866d-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="d866d-150">**Enterprise E5 ライセンスのシナリオ**</span><span class="sxs-lookup"><span data-stu-id="d866d-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="d866d-151">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="d866d-151">**License**</span></span>|<span data-ttu-id="d866d-152">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="d866d-152">**Clients**</span></span>|<span data-ttu-id="d866d-153">**メモ**</span><span class="sxs-lookup"><span data-stu-id="d866d-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d866d-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="d866d-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="d866d-155">Lync 2013 (Skype for Business 2015) は、Outlook 2013 または Outlook 2016 で使用されています。</span><span class="sxs-lookup"><span data-stu-id="d866d-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="d866d-156">Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="d866d-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="d866d-157">Skype for Business Basic クライアントは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d866d-158">Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。</span><span class="sxs-lookup"><span data-stu-id="d866d-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="d866d-159">Enterprise E5 plus Office 365 通話プラン</span><span class="sxs-lookup"><span data-stu-id="d866d-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="d866d-160">Skype for Business for Mac 2016</span><span class="sxs-lookup"><span data-stu-id="d866d-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="d866d-161">Outlook 2013 または Outlook 2016 で使用されている Lync 2013 (Skype for Business 2015)</span><span class="sxs-lookup"><span data-stu-id="d866d-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d866d-162">Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="d866d-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d866d-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d866d-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="d866d-164">Skype for Business Basic クライアントは、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d866d-165">Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。</span><span class="sxs-lookup"><span data-stu-id="d866d-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="d866d-166">委任を設定および確認する</span><span class="sxs-lookup"><span data-stu-id="d866d-166">Set up and verify delegation</span></span>

<span data-ttu-id="d866d-167">Skype for Business Online の委任を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d866d-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="d866d-168">Windows クライアントの場合</span><span class="sxs-lookup"><span data-stu-id="d866d-168">For Windows clients</span></span>

 <span data-ttu-id="d866d-169">**[着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="d866d-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="d866d-170">[**ツール** > **]** > の [**着信の転送設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d866d-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="d866d-171">[**代理人メンバーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d866d-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="d866d-172">[**追加**] を選択し、追加する代理人を選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d866d-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="d866d-173">**[着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="d866d-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="d866d-174">Outlook で、[**ファイル** > **アカウント設定** > \*\*\*\* > ] を**選択します。**</span><span class="sxs-lookup"><span data-stu-id="d866d-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="d866d-175">代理人になるユーザーの名前を探して追加します。</span><span class="sxs-lookup"><span data-stu-id="d866d-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="d866d-176">[**予定表**] メニューを選択し、[**編集] (アイテムを参照、作成、変更できる)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d866d-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="d866d-177">Mac クライアントの場合-Lync</span><span class="sxs-lookup"><span data-stu-id="d866d-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="d866d-178">**[着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="d866d-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="d866d-179">クライアントに **[代理人メンバーの編集**] リンクがある [**着信の転送**] タブがありません。また、委任者が Mac コンピューターにある場合、委任者は、委任を設定するために Windows ベースのコンピューターにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="d866d-180">これは、Mac クライアントが MAPI 接続を確立できないため、Skype for Business の委任を Outlook から確立するための要件です。</span><span class="sxs-lookup"><span data-stu-id="d866d-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="d866d-181">成功を確認する</span><span class="sxs-lookup"><span data-stu-id="d866d-181">Verify success</span></span>

<span data-ttu-id="d866d-182">セットアップが正常に完了した場合は、代理人に **< 名前>メッセージの代理人として追加され**たことと、グループ**の [通話の管理**] グループが作成されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d866d-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="d866d-183">委任者には、**代理人**グループが作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d866d-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d866d-184">委任権限は通常、セットアッププロセスで30分以内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d866d-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="d866d-185">ただし、このプロセスが完了するまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d866d-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="d866d-186">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d866d-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="d866d-187">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="d866d-187">Common issues</span></span>

- > <span data-ttu-id="d866d-188">**問題 1**委任者によって Outlook クライアントから代理人が削除された後、[グループ**の呼び出しを管理する人**] グループに代理人エントリが表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="d866d-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="d866d-189">**解像度 1**Skype for Business クライアントで、[**代理人**] グループの代理人を右クリックし、[**グループから削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d866d-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="d866d-190">**問題 2**Outlook クライアントから代理人アクセス権が付与された後は、[確認メッセージ] と [**他の人として通話を管理**する] グループは代理人に対して表示されません。</span><span class="sxs-lookup"><span data-stu-id="d866d-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="d866d-191">**解決方法 2**Outlook クライアントから委任を削除し、レプリケーションを15分ほど待ってから、もう一度代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="d866d-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="d866d-192">その他の一般的な問題</span><span class="sxs-lookup"><span data-stu-id="d866d-192">Other common issues</span></span>

- <span data-ttu-id="d866d-193">委任が機能しないのは、最大でが25個と25個のデリゲートのしきい値を超えた場合です。</span><span class="sxs-lookup"><span data-stu-id="d866d-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="d866d-194">Skype for Business Basic クライアントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d866d-195">Skype for Business Basic クライアントをインストールすると、委任が削除され、解除されます。</span><span class="sxs-lookup"><span data-stu-id="d866d-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="d866d-196">[ **MAPI Status** ] の値**が [OK]** になっていない場合は、 **SIP**と**SMTP**の値が一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d866d-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d866d-197">Skype for Business と Outlook を初めて起動した後、MAPI の状態が **[OK]** として表示されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d866d-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="d866d-198">セキュリティグループの作成とそのセキュリティグループの委任権限の追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d866d-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="d866d-199">MAPI は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d866d-199">MAPI is unavailable.</span></span> <span data-ttu-id="d866d-200">[Skype For business 2016 クライアントでの "MAPI は利用できません" エラーを](https://support.microsoft.com/en-us/help/3147130)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d866d-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="d866d-201">Skype for Business クライアントから Exchange Online メールボックスにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d866d-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="d866d-202">この問題が発生した場合は、 [Outlook 接続テスト](https://testconnectivity.microsoft.com/)を実行して、合格していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d866d-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d866d-203">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d866d-203">Related topics</span></span>
[<span data-ttu-id="d866d-204">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="d866d-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d866d-205">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="d866d-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
