---
title: Skype for Business Server でのダイヤルイン会議の PIN ポリシーの管理
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '概要: Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する方法について説明します。'
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827957"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="1be9c-103">Skype for Business Server でのダイヤルイン会議の PIN ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="1be9c-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="1be9c-104">**概要:** Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="1be9c-105">組織内の Active Directory ドメイン サービス (AD DS) 資格情報を持つ Skype for Business Server ユーザーは、暗証番号 (PIN) を使用して、認証されたユーザーとしてダイヤルイン会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="1be9c-106">PIN ポリシーは、ダイヤルイン会議 PIN の動作に関するルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="1be9c-107">組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用して、必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="1be9c-108">グローバル PIN ポリシーは、ダイヤルイン会議 PIN のルールを、フォレスト レベルで定義します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="1be9c-109">グローバル PIN ポリシーは変更できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1be9c-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="1be9c-110">特定のポリシーをサイトまたは特定のユーザー グループに適用する場合は、新しい PIN ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="1be9c-111">PIN ポリシーは、最も狭いスコープから最も広いスコープまでユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="1be9c-112">ユーザーレベルの PIN ポリシーをユーザーに割り当てると、これらの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="1be9c-113">ユーザー ポリシーを割り当てない場合は、サイト レベルの PIN ポリシーが適用されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="1be9c-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="1be9c-114">ユーザーポリシーまたはサイト ポリシーが適用されない場合、グローバル PIN ポリシーは既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="1be9c-115">PIN ポリシーに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1be9c-115">View information about PIN policies</span></span>

<span data-ttu-id="1be9c-116">PIN ポリシーに関する情報は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1be9c-117">Skype for Business Server コントロール パネルを使用して PIN ポリシーに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1be9c-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1be9c-118">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1be9c-119">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1be9c-120">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1be9c-121">[PIN **ポリシー] ページ** で、表示する PIN ポリシーをクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1be9c-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1be9c-122">Skype for Business Server 管理シェルを使用して PIN ポリシーに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="1be9c-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1be9c-123">PIN ポリシーに関する情報を表示するには **、Get-CsPinPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="1be9c-124">たとえば、次のコマンドを実行すると、site:Redmond という IDENTITY を持つ 1 つの PIN ポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="1be9c-125">完全な構文の説明やパラメーターの一覧など、詳細については [、Get-CsPinPolicy を参照してください](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1be9c-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="1be9c-126">グローバル PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1be9c-126">Modify the global PIN policy</span></span>

<span data-ttu-id="1be9c-127">グローバル PIN ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1be9c-128">Skype for Business Server コントロール パネルを使用してグローバル ダイヤルイン会議 PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1be9c-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1be9c-129">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1be9c-130">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1be9c-131">左側のナビゲーション バーで [**会議**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1be9c-132">[**PIN ポリシー**] ページで、[**グローバル**] ポリシー、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1be9c-p105">[**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。 既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="1be9c-p106">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="1be9c-138">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="1be9c-p107">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="1be9c-142">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="1be9c-p108">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="1be9c-p109">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1be9c-148">セキュリティ上の理由から、一般的なパターンは許可しないでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="1be9c-149">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1be9c-150">Skype for Business Server 管理シェルを使用してグローバル ダイヤルイン会議 PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1be9c-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1be9c-151">グローバル ダイヤルイン会議 PIN ポリシーを変更するには **、Set-CsPinPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1be9c-152">次のコマンドは、組織で使用するように構成されている PIN ポリシーすべてについて MinPasswordLength の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="1be9c-153">これを行うには、まずパラメーターを指定せずに **Get-CsPinPolicy** コマンドレットを呼び出して、すべての既存の PIN ポリシーのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="1be9c-154">次に、このコレクションを **Set-CsPinPolicy** コマンドレットにパイプ処理し、コレクション内の各ポリシーの MinPasswordLength プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="1be9c-155">完全な構文の説明やパラメーターの一覧など、詳細については [、「Set-CsPinPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1be9c-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="1be9c-156">ユーザーまたはサイトの PIN ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1be9c-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="1be9c-157">ユーザーまたはサイトの PIN ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1be9c-158">Skype for Business Server コントロール パネルを使用してユーザーまたはサイトの PIN ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1be9c-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1be9c-159">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1be9c-160">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1be9c-161">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1be9c-162">[**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="1be9c-p111">ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。 [**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="1be9c-p112">サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。 サイトの一覧で、対象のサイトをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="1be9c-168">[**説明**] フィールドに、PIN ポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="1be9c-p113">[**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。 既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="1be9c-p114">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="1be9c-174">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="1be9c-p115">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="1be9c-178">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="1be9c-p116">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="1be9c-p117">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1be9c-184">セキュリティ上の理由から、一般的なパターンは許可しないでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="1be9c-185">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1be9c-186">Skype for Business Server 管理シェルを使用してユーザーまたはサイトの PIN ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1be9c-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1be9c-187">ユーザーまたはサイトの PIN ポリシーを作成するには **、New-CsPinPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1be9c-188">次のコマンドは、site:Redmond という ID を持つ新しい PIN ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="1be9c-189">このコマンドには、オプションのパラメーター MinPasswordLength が 1 つ含まれています。MinPasswordLength プロパティを 7 に設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="1be9c-190">残りのすべてのポリシー プロパティは、既定値を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="1be9c-191">完全な構文の説明やパラメーターの一覧など、詳細については [、「New-CsPinPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1be9c-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="1be9c-192">ユーザーまたはサイトの PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1be9c-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="1be9c-193">ユーザーまたはサイトの PIN ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1be9c-194">Skype for Business Server コントロール パネルを使用してユーザーまたはサイトの PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1be9c-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1be9c-195">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1be9c-196">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1be9c-197">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1be9c-198">[**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1be9c-199">[**PIN ポリシーの編集**] で、ポリシー名以外のポリシー設定を変更します。ポリシー名は変更できません。</span><span class="sxs-lookup"><span data-stu-id="1be9c-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="1be9c-200">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1be9c-201">Skype for Business Server 管理シェルを使用してユーザーまたはサイトの PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1be9c-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1be9c-202">ダイヤルイン会議 PIN ポリシーを変更するには **、Set-CsPinPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1be9c-203">次のコマンドは、Redmond サイトに割り当てられている PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="1be9c-204">この場合、このコマンドは MinPasswordLength プロパティの値を 10 に変更します。つまり、新しい PIN には少なくとも 10 桁の数字が必要です。</span><span class="sxs-lookup"><span data-stu-id="1be9c-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="1be9c-205">完全な構文の説明やパラメーターの一覧など、詳細については [、「Set-CsPinPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1be9c-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="1be9c-206">ユーザーまたはサイトの PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="1be9c-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="1be9c-207">ユーザーまたはサイトの PIN ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1be9c-208">Skype for Business Server コントロール パネルを使用してユーザーまたはサイトの PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="1be9c-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1be9c-209">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1be9c-210">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1be9c-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1be9c-211">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1be9c-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1be9c-212">[PIN **ポリシー] ページ** で、変更する PIN ポリシーをクリックし、[編集] をクリックして、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1be9c-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1be9c-213">Skype for Business Server 管理シェルを使用してユーザーまたはサイトの PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="1be9c-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1be9c-214">ユーザーまたはサイトの PIN ポリシーを削除するには **、Remove-CsPinPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1be9c-215">次のコマンドは、サイト スコープで構成されている PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="1be9c-216">これを行うには **、Get-CsPinPolicy** コマンドレットを Filter パラメーターと共に使用して、Identity が文字 "site:" で始まるすべてのポリシーのコレクションを戻します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="1be9c-217">次に、このコレクションを **Remove-CsPinPolicy** コマンドレットにパイプ処理し、コレクション内の各ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1be9c-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="1be9c-218">完全な構文の説明やパラメーターの一覧など、詳細については [、「Remove-CsPinPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1be9c-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

