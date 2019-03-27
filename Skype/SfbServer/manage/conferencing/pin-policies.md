---
title: ビジネス サーバーの Skype では、ダイヤルイン会議の暗証番号 (pin) ポリシーを管理します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '概要: ビジネス サーバーの Skype では、ダイヤルイン会議の暗証番号 (pin) ポリシーを管理する方法を説明します。'
ms.openlocfilehash: 29fd3e2fff1628eaa96d7296e8fe9d7b9183d690
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893322"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="c13fb-103">ビジネス サーバーの Skype では、ダイヤルイン会議の暗証番号 (pin) ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="c13fb-104">**の概要:** ビジネス サーバーの Skype では、ダイヤルイン会議の暗証番号 (pin) ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="c13fb-105">組織の Active Directory ドメイン サービス (AD DS) の資格情報を持つサーバーのビジネス ユーザーの Skype は、暗証番号 (PIN) を使用して、認証済みユーザーとしてダイヤルイン会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="c13fb-106">PIN ポリシーは、ダイヤルイン会議 PIN がどのように機能するかについてのルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="c13fb-p102">組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用でき、必要に応じて変更することもできます。グローバル PIN ポリシーは、ダイヤルイン会議 PIN のルールを、フォレスト レベルで定義します。グローバル PIN ポリシーを変更することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="c13fb-110">特定のポリシーをサイトまたは特定のユーザー グループに適用する場合は、新しい PIN ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="c13fb-111">PIN ポリシーは、最も狭いスコープから最も広いスコープまでのどのスコープでも、ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="c13fb-112">ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="c13fb-113">ユーザー ポリシーを割り当てない場合は、サイトレベルの PIN ポリシーがあれば、そのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="c13fb-114">ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="c13fb-115">PIN ポリシーに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c13fb-115">View information about PIN policies</span></span>

<span data-ttu-id="c13fb-116">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、暗証番号 (pin) のポリシーに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c13fb-117">ビジネス サーバーのコントロール パネルの Skype を使用して、暗証番号 (pin) のポリシーに関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="c13fb-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c13fb-118">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="c13fb-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="c13fb-119">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c13fb-120">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c13fb-121">[**PIN ポリシー**] ページで、表示する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c13fb-122">ビジネス サーバー管理シェルの Skype を使用して、暗証番号 (pin) のポリシーに関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="c13fb-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c13fb-123">PIN ポリシーに関する情報を表示するには、**Get-CsPinPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="c13fb-124">たとえば、次のコマンドを実行すると、site:Redmond という Identity を持つ 1 つの PIN ポリシーに関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="c13fb-125">完全な構文の説明と、パラメーターの一覧を含む詳細については、 [Get CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13fb-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="c13fb-126">グローバル PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c13fb-126">Modify the global PIN policy</span></span>

<span data-ttu-id="c13fb-127">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用してグローバル PIN ポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c13fb-128">ビジネス サーバーのコントロール パネルの Skype を使用してグローバル ダイヤルイン会議 PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c13fb-129">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="c13fb-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="c13fb-130">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c13fb-131">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c13fb-132">[**PIN ポリシー**] ページで、[**グローバル**] ポリシー、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c13fb-p105">[**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="c13fb-p106">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="c13fb-138">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="c13fb-p107">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="c13fb-142">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="c13fb-p108">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="c13fb-p109">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c13fb-148">セキュリティ上の理由により、共通のパターンは許可しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="c13fb-149">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c13fb-150">Skype ビジネス サーバー管理シェルを使用してグローバル ダイヤルイン会議 PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c13fb-151">グローバル ダイヤルイン会議 PIN ポリシーを変更するには、**Set-CsPinPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c13fb-p110">次のコマンドは、組織内で使用するよう構成されているすべての PIN ポリシーの MinPasswordLength の値を変更します。これを行うため、まずパラメーターを何も指定しない **Get-CsPinPolicy** コマンドレットを呼び出して、すべての既存の PIN ポリシーのコレクションを取得しています。次に、そのコレクションを **Set-CsPinPolicy** コマンドレットにパイプ処理し、コレクション内の各ポリシーの MinPasswordLength プロパティの値を変更しています。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="c13fb-155">詳細については、完全な構文の説明と、パラメーターの一覧を含む[セット CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13fb-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="c13fb-156">ユーザーまたはサイトの PIN ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c13fb-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="c13fb-157">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c13fb-158">ビジネス サーバーのコントロール パネルの Skype を使用して、ユーザーまたはサイトの PIN ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c13fb-159">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="c13fb-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="c13fb-160">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c13fb-161">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c13fb-162">[**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c13fb-p111">ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。[**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="c13fb-p112">サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。サイトの一覧で、対象のサイトをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="c13fb-168">[**説明**] フィールドに、PIN ポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="c13fb-p113">[**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="c13fb-p114">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="c13fb-174">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="c13fb-p115">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="c13fb-178">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="c13fb-p116">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="c13fb-p117">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c13fb-184">セキュリティ上の理由により、共通のパターンは許可しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="c13fb-185">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c13fb-186">Skype ビジネス サーバー管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c13fb-187">ユーザーまたはサイトの PIN ポリシーを作成するには、**New-CsPinPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c13fb-p118">次のコマンドでは、site:Redmond という Identity を持つ新しい PIN ポリシーを作成します。このコマンドには、ただ 1 つのオプションのパラメーターである MinPasswordLength が含まれています。このパラメーターを使用して、MinPasswordLength プロパティを 7 に設定します。ポリシーの残りすべてのプロパティは、既定値を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="c13fb-191">詳細については、完全な構文の説明と、パラメーターの一覧を含む[新しい CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13fb-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="c13fb-192">ユーザーまたはサイトの PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c13fb-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="c13fb-193">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c13fb-194">ビジネス サーバーのコントロール パネルの Skype を使用して、ユーザーまたはサイトの PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c13fb-195">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="c13fb-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="c13fb-196">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c13fb-197">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c13fb-198">[**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c13fb-199">[**PIN ポリシーの編集**] で、ポリシー名以外のポリシー設定を変更します。ポリシー名は変更できません。</span><span class="sxs-lookup"><span data-stu-id="c13fb-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="c13fb-200">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c13fb-201">Skype ビジネス サーバー管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c13fb-202">ダイヤルイン会議 PIN ポリシーを変更するには、**Set-CsPinPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c13fb-p119">次のコマンドでは、Redmond サイトに割り当てた PIN ポリシーを変更しています。この例では、MinPasswordLength プロパティの値を 10 に変更しています。これは、新しい PIN を 10 桁以上にしなければならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="c13fb-205">詳細については、完全な構文の説明と、パラメーターの一覧を含む[セット CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13fb-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="c13fb-206">ユーザーまたはサイトの PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c13fb-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="c13fb-207">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c13fb-208">ビジネス サーバーのコントロール パネルの Skype を使用して、ユーザーまたはサイトの PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c13fb-209">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="c13fb-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="c13fb-210">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c13fb-211">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c13fb-212">[**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c13fb-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c13fb-213">Skype ビジネス サーバー管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c13fb-214">ユーザーまたはサイトの PIN ポリシーを削除するには、**Remove-CsPinPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c13fb-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c13fb-p120">次のコマンドは、サイト スコープで構成されていたすべての PIN ポリシーを削除します。これを実行するには、まず Filter パラメーターを指定して **Get-CsPinPolicy** コマンドレットを使用し、Identity が文字列 "site:" で始まるすべてのポリシーのコレクションを戻します。次に、このコレクションは **Remove-CsPinPolicy** コマンドレットにパイプ処理され、コレクション内の各ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c13fb-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="c13fb-218">詳細については、完全な構文の説明と、パラメーターの一覧を含む[削除 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13fb-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

