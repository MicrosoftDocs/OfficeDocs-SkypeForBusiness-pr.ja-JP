---
title: Skype for Business Server でユーザー PIN をロックまたはロック解除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議 PIN をロックまたはロック解除します。'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828367"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="c8250-103">Skype for Business Server でユーザー PIN をロックまたはロック解除する</span><span class="sxs-lookup"><span data-stu-id="c8250-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="c8250-104">**概要:** Skype for Business Server のユーザーのダイヤルイン会議 PIN をロックまたはロック解除します。</span><span class="sxs-lookup"><span data-stu-id="c8250-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8250-105">ユーザーの PIN は、Skype for Business Server コントロール パネルの **[ユーザー** ] セクションからロックまたはロック解除できます。</span><span class="sxs-lookup"><span data-stu-id="c8250-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c8250-106">Skype for Business Server コントロール パネルでユーザーの PIN をロックするには</span><span class="sxs-lookup"><span data-stu-id="c8250-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c8250-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8250-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c8250-108">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8250-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c8250-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c8250-110">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8250-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="c8250-111">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="c8250-112">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c8250-113">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="c8250-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c8250-114">a. </span><span class="sxs-lookup"><span data-stu-id="c8250-114">a.</span></span> <span data-ttu-id="c8250-115">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c8250-116">b.</span><span class="sxs-lookup"><span data-stu-id="c8250-116">b.</span></span> <span data-ttu-id="c8250-117">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8250-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c8250-118">c.</span><span class="sxs-lookup"><span data-stu-id="c8250-118">c.</span></span> <span data-ttu-id="c8250-119">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c8250-120">d. </span><span class="sxs-lookup"><span data-stu-id="c8250-120">d.</span></span> <span data-ttu-id="c8250-121">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="c8250-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8250-122">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c8250-123">e. </span><span class="sxs-lookup"><span data-stu-id="c8250-123">e.</span></span> <span data-ttu-id="c8250-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-124">Click **Find**.</span></span>
    
   <span data-ttu-id="c8250-125">f.</span><span class="sxs-lookup"><span data-stu-id="c8250-125">f.</span></span> <span data-ttu-id="c8250-126">ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c8250-127">Skype for Business Server コントロール パネルでユーザーの PIN のロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="c8250-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c8250-128">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8250-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c8250-129">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8250-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c8250-130">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c8250-131">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8250-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="c8250-132">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="c8250-133">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c8250-134">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="c8250-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c8250-135">a. </span><span class="sxs-lookup"><span data-stu-id="c8250-135">a.</span></span> <span data-ttu-id="c8250-136">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c8250-137">b.</span><span class="sxs-lookup"><span data-stu-id="c8250-137">b.</span></span> <span data-ttu-id="c8250-138">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8250-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c8250-139">c.</span><span class="sxs-lookup"><span data-stu-id="c8250-139">c.</span></span> <span data-ttu-id="c8250-140">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c8250-141">d. </span><span class="sxs-lookup"><span data-stu-id="c8250-141">d.</span></span> <span data-ttu-id="c8250-142">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="c8250-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8250-143">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c8250-144">e. </span><span class="sxs-lookup"><span data-stu-id="c8250-144">e.</span></span> <span data-ttu-id="c8250-145">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-145">Click **Find**.</span></span>
    
   <span data-ttu-id="c8250-146">f.</span><span class="sxs-lookup"><span data-stu-id="c8250-146">f.</span></span> <span data-ttu-id="c8250-147">ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8250-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8250-148">コマンドレットを使用したユーザー PIN のロックWindows PowerShell解除</span><span class="sxs-lookup"><span data-stu-id="c8250-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c8250-149">ユーザー PIN のロックとロック解除は、Windows PowerShellコマンドレットと Lock-CsClientPinコマンドレットUnlock-CsClientPinできます。</span><span class="sxs-lookup"><span data-stu-id="c8250-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="c8250-150">これらのコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c8250-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8250-151">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8250-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c8250-152">プロセスは Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="c8250-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="c8250-153">ユーザー PIN をロックするには</span><span class="sxs-lookup"><span data-stu-id="c8250-153">To lock a user PIN</span></span>

- <span data-ttu-id="c8250-154">ユーザーの PIN をロックするには、次のコマンドレットLock-CsClientPinします。</span><span class="sxs-lookup"><span data-stu-id="c8250-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="c8250-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c8250-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="c8250-156">ユーザー PIN のロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="c8250-156">To unlock a user PIN</span></span>

- <span data-ttu-id="c8250-157">ユーザーの PIN のロックを解除するには、次のコマンドレットUnlock-CsClientPinします。</span><span class="sxs-lookup"><span data-stu-id="c8250-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="c8250-158">例:</span><span class="sxs-lookup"><span data-stu-id="c8250-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="c8250-159">詳細については [、Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) コマンドレットと [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8250-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
