---
title: 設定し、Skype のオンライン ビジネスの委任のトラブルシューティング
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
description: この資料を設定し、オンライン ビジネスの委任のため Skype をトラブルシューティングする方法について説明します。 この記事では、設定の推奨事項、ベスト ・ プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。
ms.openlocfilehash: 343559110b5026f09b22f8f85d6fc95b19abedb6
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="fb1e2-104">設定し、Skype のオンライン ビジネスの委任のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fb1e2-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="fb1e2-105">この資料を設定し、オンライン ビジネスの委任のため Skype をトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="fb1e2-106">この記事では、設定の推奨事項、ベスト ・ プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="fb1e2-107">ガイドラインと要件</span><span class="sxs-lookup"><span data-stu-id="fb1e2-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="fb1e2-108">委任のためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="fb1e2-108">Guidelines for delegation</span></span>

<span data-ttu-id="fb1e2-109">設定して、委任が正しく機能するを取得するには、これらのガイドラインに従う場合に依存します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="fb1e2-110">必要がありますを使用するビジネス 2015年最新の更新プログラムの完全なクライアントの Skype または、Skype ビジネス 2016年完全なクライアントの。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="fb1e2-111">最新の更新プログラムで Outlook 2013 クライアントまたは Outlook 2016 クライアントを使っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="fb1e2-112">委任者と代理人のコンピューターがある 1 つの Outlook メール プロファイルがプライマリまたは既定のプロファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="fb1e2-113">そのメール プロファイルは、1 つだけアカウントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="fb1e2-114">代理人と代理人のための Skype では、オンライン ユーザーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="fb1e2-115">また、両方オンラインにするか両方に設置する必要があります、各アカウントの Exchange Server メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="fb1e2-116">委任者と代理人の両方に同じメジャー バージョンの Outlook を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="fb1e2-117">**True**クライアント ポリシーでは、 **EnableExchangeDelegateSync**属性の値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="fb1e2-118">この設定を確認するには、ビジネス オンラインの PowerShell モジュールの Skype で**Get CSClientPolicy**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="fb1e2-119">委任者と代理人署名が必要 Skype をビジネスおよび Outlook を同時に別のワークステーションで。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="fb1e2-120">共有メールボックスは、オンライン ビジネスの委任のための Skype のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="fb1e2-121">共有メールボックスは、 **sendonbehalf**のアクセス制御リスト (ACL) を持っていないためにです。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="fb1e2-122">ビジネス クライアントのバージョンをサポートするための Skype</span><span class="sxs-lookup"><span data-stu-id="fb1e2-122">Skype for Business client version support</span></span>

||<span data-ttu-id="fb1e2-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-123">**Outlook 2013**</span></span>|<span data-ttu-id="fb1e2-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb1e2-125">**Lync と Skype クライアントの基本的なビジネスの**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="fb1e2-126">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="fb1e2-126">Not supported</span></span> |<span data-ttu-id="fb1e2-127">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="fb1e2-127">Not supported</span></span>
|<span data-ttu-id="fb1e2-128">**ビジネス 2015年の Skype**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="fb1e2-129">サポート対象</span><span class="sxs-lookup"><span data-stu-id="fb1e2-129">Supported</span></span>| <span data-ttu-id="fb1e2-130">サポート対象</span><span class="sxs-lookup"><span data-stu-id="fb1e2-130">Supported</span></span>|
|<span data-ttu-id="fb1e2-131">**ビジネス 2016年の Skype**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="fb1e2-132">サポート対象</span><span class="sxs-lookup"><span data-stu-id="fb1e2-132">Supported</span></span>| <span data-ttu-id="fb1e2-133">サポート対象</span><span class="sxs-lookup"><span data-stu-id="fb1e2-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="fb1e2-134">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="fb1e2-134">Licensing requirements</span></span>

<span data-ttu-id="fb1e2-135">**E3 のエンタープライズ ライセンスのシナリオ**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="fb1e2-136">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-136">**License**</span></span>|<span data-ttu-id="fb1e2-137">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-137">**Clients**</span></span>|<span data-ttu-id="fb1e2-138">**メモ**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb1e2-139">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="fb1e2-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="fb1e2-140">Outlook 2013 または 2016 の Outlook で使用される Lync 2013 (Skype ビジネス 2015年の)</span><span class="sxs-lookup"><span data-stu-id="fb1e2-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb1e2-141">Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype</span><span class="sxs-lookup"><span data-stu-id="fb1e2-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fb1e2-142">ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb1e2-143">Mac クライアントは、呼び出しがない会議に委任できます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fb1e2-144">Office 365 の電話システムと Office 365 xCalling プランとエンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="fb1e2-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="fb1e2-145">Outlook 2013 または 2016 の Outlook で使用される Lync 2013 (Skype ビジネス 2015年の)</span><span class="sxs-lookup"><span data-stu-id="fb1e2-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb1e2-146">Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype</span><span class="sxs-lookup"><span data-stu-id="fb1e2-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb1e2-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fb1e2-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fb1e2-148">ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb1e2-149">Mac クライアントは、呼び出しがない会議に委任できます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="fb1e2-150">**E5 のエンタープライズ ライセンスのシナリオ**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="fb1e2-151">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-151">**License**</span></span>|<span data-ttu-id="fb1e2-152">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-152">**Clients**</span></span>|<span data-ttu-id="fb1e2-153">**メモ**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb1e2-154">エンタープライズ E5</span><span class="sxs-lookup"><span data-stu-id="fb1e2-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="fb1e2-155">Lync 2013 (ビジネス 2015年の Skype) 2013 の Outlook または Outlook 2016 を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="fb1e2-156">Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype</span><span class="sxs-lookup"><span data-stu-id="fb1e2-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fb1e2-157">ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb1e2-158">Mac クライアントは、呼び出しがない会議に委任できます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fb1e2-159">エンタープライズ E5 と Office 365 の通話プラン</span><span class="sxs-lookup"><span data-stu-id="fb1e2-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="fb1e2-160">Mac 2016 のための Skype</span><span class="sxs-lookup"><span data-stu-id="fb1e2-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="fb1e2-161">Outlook 2013 または 2016 の Outlook で使用される Lync 2013 (Skype ビジネス 2015年の)</span><span class="sxs-lookup"><span data-stu-id="fb1e2-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb1e2-162">Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype</span><span class="sxs-lookup"><span data-stu-id="fb1e2-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb1e2-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fb1e2-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fb1e2-164">ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb1e2-165">Mac クライアントは、呼び出しがない会議に委任できます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="fb1e2-166">設定し、委任の確認</span><span class="sxs-lookup"><span data-stu-id="fb1e2-166">Set up and verify delegation</span></span>

<span data-ttu-id="fb1e2-167">オンライン ビジネスの委任のために、Skype を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="fb1e2-168">Windows クライアントの</span><span class="sxs-lookup"><span data-stu-id="fb1e2-168">For Windows clients</span></span>

 <span data-ttu-id="fb1e2-169">**着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fb1e2-170">**ツール**を選択して > **オプション** > **の設定の転送を呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="fb1e2-171">**自分の代理人のメンバーを編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="fb1e2-172">**追加**] を選択、追加する代理人を選択し、 **[ok]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="fb1e2-173">**呼び出しの転送タブが表示されません。**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fb1e2-174">Outlook では、**ファイル**を選択します > **アカウントの設定** > **代理人アクセス** > **追加**します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="fb1e2-175">見つけるし、代理人になる人の名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="fb1e2-176">[**予定表**] メニューを選択し、選択**エディター (読み取り、作成、および変更できますアイテム)**。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="fb1e2-177">Mac クライアントの Lync の</span><span class="sxs-lookup"><span data-stu-id="fb1e2-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="fb1e2-178">**着信の転送] タブ**</span><span class="sxs-lookup"><span data-stu-id="fb1e2-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="fb1e2-179">クライアントは、[**自分の代理人のメンバーを編集**] リンクを持つ**呼び出しの転送**] タブがありません、代理人が Mac コンピューター上にある場合は、代理人にサインインしなければなりません、Windows ベースのコンピューターで委任を設定するのには。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="fb1e2-180">Mac クライアントは、MAPI 接続をすることはできませんし、これは、Outlook からの業務の委任のため Skype を確立する必要があるためにです。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="fb1e2-181">成功を確認します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-181">Verify success</span></span>

<span data-ttu-id="fb1e2-182">**< 名前 > の代理人として追加された**のは、代理人は見る必要があります、セットアップが成功した場合は、メッセージ、および**呼び出しの管理の人に**グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="fb1e2-183">代理人は**代理人**のグループが作成されるはずです。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb1e2-184">委任アクセス許可は、通常のセットアップ プロセスの 30 分以内で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="fb1e2-185">ただし、最大 24 時間かかることができます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="fb1e2-186">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fb1e2-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="fb1e2-187">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="fb1e2-187">Common issues</span></span>

- > <span data-ttu-id="fb1e2-188">**問題 1**代理エントリに引き続き表示されます**呼び出しの管理の人が私**のグループ、代理人が Outlook クライアントからデリゲートを削除後します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="fb1e2-189">**解決方法 1**ビジネス クライアント用の Skype で [**代理人**] で、代理人を右クリックし [**グループから削除**します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="fb1e2-190">**問題 2**Outlook クライアントを代理人アクセスが許可されると後は、代理人の確認のメッセージも、**呼び出しの管理の人が私**のグループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="fb1e2-191">**解決方法 2**Outlook クライアントからの委任を削除して、レプリケーションは、約 15 分間待ちます、代理人を追加し直す。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="fb1e2-192">その他の一般的な問題</span><span class="sxs-lookup"><span data-stu-id="fb1e2-192">Other common issues</span></span>

- <span data-ttu-id="fb1e2-193">25 委任者と代理人の 25 のしきい値を超えた場合、委任が動作しません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="fb1e2-194">ビジネスの基本的なクライアントの Skype はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb1e2-195">ビジネスの基本的なクライアントの Skype をインストールするは削除して、委任を解除します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="fb1e2-196">**MAPI のステータス**値には、 **[ok]**がない場合は、 **SIP**と**SMTP**の値と一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb1e2-197">ビジネスおよび Outlook の Skype を初めて起動した後、 **[ok]**として表示するのには MAPI の状態までに数分かかることができます。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="fb1e2-198">セキュリティ グループを作成し、そのセキュリティ グループのアクセス許可を委任を追加することがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="fb1e2-199">MAPI が使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-199">MAPI is unavailable.</span></span> <span data-ttu-id="fb1e2-200">[Skype ビジネス 2016年のクライアントで"MAPI を使用できません"エラー](https://support.microsoft.com/en-us/help/3147130)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="fb1e2-201">Exchange Online のメールボックスは、ビジネス クライアント用の Skype を介してアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="fb1e2-202">この問題が発生した場合は、 [Outlook の [接続のテスト](https://testconnectivity.microsoft.com/)に合格したことを確認するを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb1e2-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fb1e2-203">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fb1e2-203">Related topics</span></span>
[<span data-ttu-id="fb1e2-204">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fb1e2-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fb1e2-205">Skype for Business ユーザーが Skype 連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="fb1e2-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 