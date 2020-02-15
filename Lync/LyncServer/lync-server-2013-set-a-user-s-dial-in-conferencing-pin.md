---
title: 'Lync Server 2013: ユーザーのダイヤルイン会議の PIN の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c344a848050d53027c094ad549f0285fbae09489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="409e9-102">Lync Server 2013 でユーザーのダイヤルイン会議の PIN を設定する</span><span class="sxs-lookup"><span data-stu-id="409e9-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="409e9-103">_**トピックの最終更新日:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="409e9-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="409e9-104">認証されたユーザーとしてダイヤルイン会議に参加するには、Lync Server 2013 ユーザーに Active Directory ドメインサービス (AD DS) の資格情報が必要です。個人識別番号 (PIN) が必要です。</span><span class="sxs-lookup"><span data-stu-id="409e9-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="409e9-105">ユーザーがダイヤルイン会議 PIN を忘れた場合、または Lync Server を使用して PIN を設定していない場合は、Lync Server コントロールパネルでユーザーの PIN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="409e9-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="409e9-106">PIN は自動で生成することも手動で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="409e9-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="409e9-107">最小サイズなど、PIN の具体的な特性は、ポリシーとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="409e9-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="409e9-108">グローバル ポリシーに加えて、個々のサイトまたはユーザーを対象にした PIN ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="409e9-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="409e9-109">PIN ポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409e9-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="409e9-110">ユーザーの PIN を設定するには</span><span class="sxs-lookup"><span data-stu-id="409e9-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="409e9-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="409e9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="409e9-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="409e9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="409e9-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409e9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="409e9-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="409e9-115">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="409e9-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="409e9-116">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="409e9-117">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="409e9-118">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="409e9-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="409e9-119">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="409e9-120">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="409e9-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="409e9-121">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**] または [**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="409e9-122">選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="409e9-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="409e9-123">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="409e9-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="409e9-p104">PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。 PIN のロックを解除するには、ユーザーをクリックし、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>PIN のロック解除</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="409e9-127">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**暗証番号 (PIN) の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="409e9-128">[**暗証番号 (PIN) の設定**] ダイアログ ボックスで、次のどちらかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="409e9-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="409e9-129">Lync Server 2013 でユーザーの PIN を生成できるようにするには、[**有効な pin を自動的に生成**する] を選択します (既定値)。</span><span class="sxs-lookup"><span data-stu-id="409e9-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="409e9-130">自分の PIN を作成するには、[**特定の PIN を手動で入力**] をクリックして、テキスト ボックスをクリックし、PIN のポリシー設定で指定されている PIN の要件を満たす PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="409e9-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="409e9-131">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-131">Click **OK**.</span></span>

9.  <span data-ttu-id="409e9-132">[**暗証番号 (PIN) の設定**] で、次のどちらかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="409e9-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="409e9-133">[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、PIN をコピーし、組織で推奨される方法を使用しているユーザーに伝えます。</span><span class="sxs-lookup"><span data-stu-id="409e9-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="409e9-p105">PIN を電子メールで送信するには、[**新しい PIN をユーザーに送信するために電子メール アプリケーションを開く**] をクリックします。 使用している電子メール クライアントが Microsoft Office Outlook の場合、PIN は新しい電子メール メッセージに自動的にコピーされます。 他の電子メール クライアントを使用している場合は、[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、電子メール メッセージにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="409e9-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="409e9-137">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409e9-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="409e9-138">Windows PowerShell コマンドレットを使用してユーザー PIN を割り当てる</span><span class="sxs-lookup"><span data-stu-id="409e9-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="409e9-139">PIN 番号を割り当てるには、コマンドレットの設定を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="409e9-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="409e9-140">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="409e9-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="409e9-141">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="409e9-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="409e9-142">PIN 番号をユーザーに自動的に割り当てるには</span><span class="sxs-lookup"><span data-stu-id="409e9-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="409e9-143">次のコマンドでは、PIN 番号を Ken Myer というユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="409e9-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="409e9-144">Pin パラメーターは含まれていないため、Lync Server は PIN 番号を自動的に生成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="409e9-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="409e9-145">特定の PIN 番号をユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="409e9-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="409e9-146">このコマンドでは、Pin パラメーターを使用して PIN 番号 121989 を Ken Myer というユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="409e9-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="409e9-147">詳細については、「 [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="409e9-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="409e9-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="409e9-148">See Also</span></span>


<span data-ttu-id="409e9-149">[ダイヤルイン アクセス番号](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="409e9-149">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="409e9-150">Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="409e9-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

