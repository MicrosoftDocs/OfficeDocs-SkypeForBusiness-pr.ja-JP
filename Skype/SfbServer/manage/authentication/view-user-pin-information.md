---
title: Skype for Business Server でユーザーの PIN 情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: '概要: Skype for Business Server でユーザーの PIN 情報を表示します。'
ms.openlocfilehash: e0a74d980be4c77c5fe92f9e0d871f238a7271f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991942"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="df47e-103">Skype for Business Server でユーザーの PIN 情報を表示する</span><span class="sxs-lookup"><span data-stu-id="df47e-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="df47e-104">**概要:** Skype for Business Server でユーザーの PIN 情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="df47e-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="df47e-105">認証されたユーザーとしてダイヤルイン会議に参加するには、Skype for Business Server ユーザー (Active Directory ドメインサービス (AD DS) の資格情報に暗証番号 (PIN) が必要です。</span><span class="sxs-lookup"><span data-stu-id="df47e-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="df47e-106">Skype for Business Server コントロールパネルからユーザーの PIN 情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="df47e-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df47e-107">PIN が設定されているかどうかや PIN の最終変更日時などの PIN 状態情報を表示することはできますが、PIN の状態を調べても最新の PIN は確認できません。</span><span class="sxs-lookup"><span data-stu-id="df47e-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="df47e-108">ユーザーが PIN を紛失した場合は、「 [Skype For Business Server でユーザーのダイヤルイン会議 PIN を設定](set-a-user-s-dial-in-conferencing-pin.md)する」の手順に従ってリセットできます。</span><span class="sxs-lookup"><span data-stu-id="df47e-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="df47e-109">Skype for Business Server コントロールパネルでユーザーの PIN を表示するには</span><span class="sxs-lookup"><span data-stu-id="df47e-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="df47e-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="df47e-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="df47e-111">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="df47e-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="df47e-112">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="df47e-113">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="df47e-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="df47e-114">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="df47e-115">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="df47e-116">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="df47e-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="df47e-117">a.</span><span class="sxs-lookup"><span data-stu-id="df47e-117">a.</span></span> <span data-ttu-id="df47e-118">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="df47e-119">b.</span><span class="sxs-lookup"><span data-stu-id="df47e-119">b.</span></span> <span data-ttu-id="df47e-120">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="df47e-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="df47e-121">c.</span><span class="sxs-lookup"><span data-stu-id="df47e-121">c.</span></span> <span data-ttu-id="df47e-122">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="df47e-123">d.</span><span class="sxs-lookup"><span data-stu-id="df47e-123">d.</span></span> <span data-ttu-id="df47e-124">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="df47e-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="df47e-125">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="df47e-126">•.</span><span class="sxs-lookup"><span data-stu-id="df47e-126">e.</span></span> <span data-ttu-id="df47e-127">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df47e-p108">PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。PIN のロックを解除するには、ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="df47e-130">検索結果でユーザーをクリックし、[**アクション**] をクリックして、[**PIN の状態を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df47e-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df47e-131">Windows PowerShell コマンドレットを使用してユーザーの PIN 情報を表示する</span><span class="sxs-lookup"><span data-stu-id="df47e-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="df47e-132">Get-CsClientPinInfo コマンドレットを使用して、ユーザーの PIN 情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="df47e-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="df47e-133">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="df47e-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df47e-134">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df47e-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="df47e-135">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="df47e-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="df47e-136">ユーザーの PIN 情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="df47e-136">To view user PIN information</span></span>

<span data-ttu-id="df47e-137">ユーザーの PIN 情報を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="df47e-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="df47e-138">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df47e-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="df47e-139">詳細については、 [CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df47e-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df47e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="df47e-140">See also</span></span>

[<span data-ttu-id="df47e-141">Skype for Business Server でユーザーのダイヤルイン会議の PIN を設定する</span><span class="sxs-lookup"><span data-stu-id="df47e-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="df47e-142">Skype for Business Server でユーザー PIN をロックまたはロック解除する</span><span class="sxs-lookup"><span data-stu-id="df47e-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
