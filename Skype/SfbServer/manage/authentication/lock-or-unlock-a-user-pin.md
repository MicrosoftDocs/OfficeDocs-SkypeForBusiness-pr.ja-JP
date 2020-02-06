---
title: Skype for Business Server でユーザー PIN をロックまたはロック解除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議の PIN をロックまたはロック解除します。'
ms.openlocfilehash: e9a5e59497a4cb771d0b20cef55b09b26817216d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818789"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="bc674-103">Skype for Business Server でユーザー PIN をロックまたはロック解除する</span><span class="sxs-lookup"><span data-stu-id="bc674-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="bc674-104">**概要:** Skype for Business Server のユーザーのダイヤルイン会議の PIN をロックまたはロック解除します。</span><span class="sxs-lookup"><span data-stu-id="bc674-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="bc674-105">Skype for Business Server コントロールパネルの [**ユーザー** ] セクションで、ユーザーの PIN をロックまたはロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="bc674-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="bc674-106">Skype for Business Server コントロールパネルでユーザーの PIN をロックするには</span><span class="sxs-lookup"><span data-stu-id="bc674-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bc674-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bc674-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bc674-108">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bc674-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bc674-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="bc674-110">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc674-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="bc674-111">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="bc674-112">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="bc674-113">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="bc674-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="bc674-114">a.</span><span class="sxs-lookup"><span data-stu-id="bc674-114">a.</span></span> <span data-ttu-id="bc674-115">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="bc674-116">b.</span><span class="sxs-lookup"><span data-stu-id="bc674-116">b.</span></span> <span data-ttu-id="bc674-117">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc674-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="bc674-118">c.</span><span class="sxs-lookup"><span data-stu-id="bc674-118">c.</span></span> <span data-ttu-id="bc674-119">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="bc674-120">d.</span><span class="sxs-lookup"><span data-stu-id="bc674-120">d.</span></span> <span data-ttu-id="bc674-121">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="bc674-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bc674-122">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="bc674-123">•.</span><span class="sxs-lookup"><span data-stu-id="bc674-123">e.</span></span> <span data-ttu-id="bc674-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-124">Click **Find**.</span></span>
    
   <span data-ttu-id="bc674-125">f.</span><span class="sxs-lookup"><span data-stu-id="bc674-125">f.</span></span> <span data-ttu-id="bc674-126">ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="bc674-127">Skype for Business Server コントロールパネルでユーザーの PIN のロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="bc674-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bc674-128">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bc674-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bc674-129">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bc674-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bc674-130">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="bc674-131">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc674-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="bc674-132">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="bc674-133">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="bc674-134">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="bc674-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="bc674-135">a.</span><span class="sxs-lookup"><span data-stu-id="bc674-135">a.</span></span> <span data-ttu-id="bc674-136">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="bc674-137">b.</span><span class="sxs-lookup"><span data-stu-id="bc674-137">b.</span></span> <span data-ttu-id="bc674-138">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc674-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="bc674-139">c.</span><span class="sxs-lookup"><span data-stu-id="bc674-139">c.</span></span> <span data-ttu-id="bc674-140">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="bc674-141">d.</span><span class="sxs-lookup"><span data-stu-id="bc674-141">d.</span></span> <span data-ttu-id="bc674-142">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="bc674-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bc674-143">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="bc674-144">•.</span><span class="sxs-lookup"><span data-stu-id="bc674-144">e.</span></span> <span data-ttu-id="bc674-145">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-145">Click **Find**.</span></span>
    
   <span data-ttu-id="bc674-146">f.</span><span class="sxs-lookup"><span data-stu-id="bc674-146">f.</span></span> <span data-ttu-id="bc674-147">ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc674-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bc674-148">Windows PowerShell コマンドレットを使用したユーザー Pin のロックとロック解除</span><span class="sxs-lookup"><span data-stu-id="bc674-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bc674-149">Windows PowerShell を使用して、ユーザーピンのロックとロック解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bc674-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="bc674-150">これらのコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc674-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bc674-151">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc674-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bc674-152">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="bc674-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="bc674-153">ユーザー PIN をロックするには</span><span class="sxs-lookup"><span data-stu-id="bc674-153">To lock a user PIN</span></span>

- <span data-ttu-id="bc674-154">ユーザーの PIN をロックするには、Lock-CsClientPin コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc674-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="bc674-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bc674-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="bc674-156">ユーザー PIN のロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="bc674-156">To unlock a user PIN</span></span>

- <span data-ttu-id="bc674-157">ユーザーの PIN のロックを解除するには、[ロック解除] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc674-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="bc674-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bc674-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="bc674-159">詳細については、「[ロック-csclientpin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)と[csclientpin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)のコマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc674-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
