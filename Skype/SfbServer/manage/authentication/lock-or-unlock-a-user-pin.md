---
title: ロックまたはビジネスのサーバーのユーザーの Skype では、暗証番号 (pin) のロックを解除
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: ロックまたは、Skype のビジネス サーバーのユーザーのダイヤルイン会議 PIN のロックを解除します。'
ms.openlocfilehash: 89e971ac8c935c7998c206ce365c8899e0617cc4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986324"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="db0ea-103">ロックまたはビジネスのサーバーのユーザーの Skype では、暗証番号 (pin) のロックを解除</span><span class="sxs-lookup"><span data-stu-id="db0ea-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="db0ea-104">**の概要:** ロックまたは、Skype のビジネス サーバーのユーザーのダイヤルイン会議 PIN のロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="db0ea-105">ビジネス サーバーのコントロール パネルの Skype の**ユーザー** ] セクションから、ユーザーの PIN をロック解除またはロックできます。</span><span class="sxs-lookup"><span data-stu-id="db0ea-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="db0ea-106">Skype のビジネス サーバーのコントロール パネルのユーザーの暗証番号 (pin) をロックするのには</span><span class="sxs-lookup"><span data-stu-id="db0ea-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="db0ea-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="db0ea-108">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="db0ea-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="db0ea-110">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="db0ea-111">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="db0ea-112">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="db0ea-113">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="db0ea-114">a.</span><span class="sxs-lookup"><span data-stu-id="db0ea-114">a.</span></span> <span data-ttu-id="db0ea-115">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="db0ea-116">b.</span><span class="sxs-lookup"><span data-stu-id="db0ea-116">b.</span></span> <span data-ttu-id="db0ea-117">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="db0ea-118">c.</span><span class="sxs-lookup"><span data-stu-id="db0ea-118">c.</span></span> <span data-ttu-id="db0ea-119">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="db0ea-120">d.</span><span class="sxs-lookup"><span data-stu-id="db0ea-120">d.</span></span> <span data-ttu-id="db0ea-121">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="db0ea-122">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="db0ea-123">e。</span><span class="sxs-lookup"><span data-stu-id="db0ea-123">e.</span></span> <span data-ttu-id="db0ea-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-124">Click **Find**.</span></span>
    
   <span data-ttu-id="db0ea-125">f。</span><span class="sxs-lookup"><span data-stu-id="db0ea-125">f.</span></span> <span data-ttu-id="db0ea-126">ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="db0ea-127">ビジネス サーバーのコントロール パネルの Skype でのユーザーの暗証番号 (pin) のロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="db0ea-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="db0ea-128">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="db0ea-129">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="db0ea-130">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="db0ea-131">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="db0ea-132">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="db0ea-133">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="db0ea-134">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="db0ea-135">a.</span><span class="sxs-lookup"><span data-stu-id="db0ea-135">a.</span></span> <span data-ttu-id="db0ea-136">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="db0ea-137">b.</span><span class="sxs-lookup"><span data-stu-id="db0ea-137">b.</span></span> <span data-ttu-id="db0ea-138">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="db0ea-139">c.</span><span class="sxs-lookup"><span data-stu-id="db0ea-139">c.</span></span> <span data-ttu-id="db0ea-140">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="db0ea-141">d.</span><span class="sxs-lookup"><span data-stu-id="db0ea-141">d.</span></span> <span data-ttu-id="db0ea-142">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="db0ea-143">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="db0ea-144">e。</span><span class="sxs-lookup"><span data-stu-id="db0ea-144">e.</span></span> <span data-ttu-id="db0ea-145">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-145">Click **Find**.</span></span>
    
   <span data-ttu-id="db0ea-146">f。</span><span class="sxs-lookup"><span data-stu-id="db0ea-146">f.</span></span> <span data-ttu-id="db0ea-147">ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db0ea-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="db0ea-148">Windows PowerShell コマンドレットを使用してユーザー Pin のロックとロック解除</span><span class="sxs-lookup"><span data-stu-id="db0ea-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="db0ea-149">ロックし、Windows PowerShell と - CsClientPin のロックとロック解除 CsClientPin コマンドレットを使用してユーザー Pin のロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="db0ea-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="db0ea-150">実行できますこれらのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="db0ea-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="db0ea-151">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db0ea-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="db0ea-152">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="db0ea-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="db0ea-153">ユーザー PIN をロックするには</span><span class="sxs-lookup"><span data-stu-id="db0ea-153">To lock a user PIN</span></span>

- <span data-ttu-id="db0ea-154">ユーザーの暗証番号 (pin) をロックするには、ロック CsClientPin コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="db0ea-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="db0ea-156">ユーザー PIN のロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="db0ea-156">To unlock a user PIN</span></span>

- <span data-ttu-id="db0ea-157">ユーザーの暗証番号 (pin) のロックを解除するには、ロック解除 CsClientPin コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="db0ea-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="db0ea-158">例:</span><span class="sxs-lookup"><span data-stu-id="db0ea-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="db0ea-159">詳細については、 [- CsClientPin のロック](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)と[ロック解除 CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db0ea-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>