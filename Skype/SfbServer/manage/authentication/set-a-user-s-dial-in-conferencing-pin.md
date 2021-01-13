---
title: Skype for Business Server でユーザーのダイヤルイン会議 PIN を設定する
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議 PIN を設定します。'
ms.openlocfilehash: cd7375519fa9fc161c6414dcf1b9d0fbf6de6ef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828302"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="3f7c8-103">Skype for Business Server でユーザーのダイヤルイン会議 PIN を設定する</span><span class="sxs-lookup"><span data-stu-id="3f7c8-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="3f7c8-104">**概要:** Skype for Business Server のユーザーのダイヤルイン会議 PIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="3f7c8-105">認証されたユーザーとしてダイヤルイン会議に参加するには、Active Directory ドメイン サービス (AD DS) 資格情報を持つ Skype for Business Server ユーザーに暗証番号 (PIN) が必要です。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="3f7c8-106">ユーザーがダイヤルイン会議 PIN を忘れた場合、または Skype for Business Server を使用して PIN を設定していない場合は、Skype for Business Server コントロール パネルからユーザーの PIN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3f7c8-107">PIN は自動で生成することも手動で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f7c8-108">最小サイズなど、PIN の具体的な特性は、ポリシーとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="3f7c8-109">グローバル ポリシーに加えて、個々のサイトまたはユーザーを対象にした PIN ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="3f7c8-110">ユーザーの PIN を設定するには</span><span class="sxs-lookup"><span data-stu-id="3f7c8-110">To set a user's PIN</span></span>

1. <span data-ttu-id="3f7c8-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3f7c8-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3f7c8-113">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3f7c8-114">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="3f7c8-115">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="3f7c8-116">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="3f7c8-117">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="3f7c8-118">a. </span><span class="sxs-lookup"><span data-stu-id="3f7c8-118">a.</span></span> <span data-ttu-id="3f7c8-119">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="3f7c8-120">b.</span><span class="sxs-lookup"><span data-stu-id="3f7c8-120">b.</span></span> <span data-ttu-id="3f7c8-121">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="3f7c8-122">c.</span><span class="sxs-lookup"><span data-stu-id="3f7c8-122">c.</span></span> <span data-ttu-id="3f7c8-123">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="3f7c8-124">d. </span><span class="sxs-lookup"><span data-stu-id="3f7c8-124">d.</span></span> <span data-ttu-id="3f7c8-125">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3f7c8-126">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="3f7c8-127">e. </span><span class="sxs-lookup"><span data-stu-id="3f7c8-127">e.</span></span> <span data-ttu-id="3f7c8-128">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3f7c8-p108">PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。 PIN のロックを解除するには、ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="3f7c8-131">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**暗証番号 (PIN) の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="3f7c8-132">[**暗証番号 (PIN) の設定**] ダイアログ ボックスで、次のどちらかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="3f7c8-133">Skype for Business Server でユーザーの PIN の生成を許可するには、有効な PIN を **自動的** に生成する (既定) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="3f7c8-134">自分の PIN を作成するには、[**特定の PIN を手動で入力**] をクリックして、テキスト ボックスをクリックし、PIN のポリシー設定で指定されている PIN の要件を満たす PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="3f7c8-135">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="3f7c8-136">[**暗証番号 (PIN) の設定**] で、次のどちらかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="3f7c8-137">[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、PIN をコピーし、組織で推奨される方法を使用しているユーザーに伝えます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="3f7c8-p109">PIN を電子メールで送信するには、[**新しい PIN をユーザーに送信するために電子メール アプリケーションを開く**] をクリックします。 使用している電子メール クライアントが Microsoft Office Outlook の場合、PIN は新しい電子メール メッセージに自動的にコピーされます。 他の電子メール クライアントを使用している場合は、[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、電子メール メッセージにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="3f7c8-141">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3f7c8-142">コマンドレットを使用してユーザー PIN をWindows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="3f7c8-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3f7c8-143">このコマンドレットを使用して、PIN 番号を割り当Set-CsClientPinすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="3f7c8-144">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3f7c8-145">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3f7c8-146">プロセスは Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="3f7c8-147">PIN 番号をユーザーに自動割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3f7c8-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="3f7c8-148">次のコマンドでは、PIN 番号を Ken Myer というユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="3f7c8-149">Pin パラメーターは含まれていないため、Skype for Business Server は PIN 番号を自動的に生成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="3f7c8-150">特定の PIN 番号をユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3f7c8-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="3f7c8-151">このコマンドでは、Pin パラメーターを使用して PIN 番号 121989 を Ken Myer というユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="3f7c8-152">詳細については [、Set-CsClientPin コマンドレットのヘルプ トピックを参照](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c8-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

