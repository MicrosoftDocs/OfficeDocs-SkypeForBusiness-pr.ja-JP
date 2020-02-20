---
title: 会議の構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6906331e8a0b2cf67c8d4c0404caf2816f441ea0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2ba12-102">Lync Server 2013 で会議の構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2ba12-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba12-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2ba12-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2ba12-p101">[会議の構成] ページの設定を使って、会議の参加に関する操作性のさまざまな特性を定義できます。既定では、グローバル設定が参加に関する操作性を定義していますが、サイト レベルとプール レベルの会議参加設定を作成することもできます。プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p101">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience. By default, the global settings define the join experience. You can also create site-level and pool-level meeting join settings. If you create pool-level settings, those settings apply to all meetings hosted by that pool. If you do not create pool-level settings, site-level settings apply, if they exist. If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="2ba12-110">新しい会議参加設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="2ba12-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="2ba12-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ba12-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ba12-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba12-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ba12-114">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="2ba12-115">[**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="2ba12-p103">サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2ba12-p104">プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="2ba12-p105">公衆交換電話網 (PSTN) からダイヤルインする参加者をロビーを介してルーティングするには、[**PSTN 発信者はロビーをバイパスする**] チェック ボックスをオフにします。既定では、PSTN からダイヤルインした参加者は会議に直接移動します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="2ba12-124">会議の発表者になることができるユーザーを構成するには、[**発表者として指定**] で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="2ba12-125">開催者以外のユーザーが発表者になることを許可しない場合は、[**なし**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="2ba12-p106">組織のメンバーになっている参加者にのみ発表者になることを許可する場合は、[**会社**] をクリックします。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="2ba12-128">参加者すべてに発表者になることを許可する場合は、[**全員**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="2ba12-p107">開催者が会議のスケジュール時に会議の種類を選択できるようにするには、[**既定で割り当てられた会議の種類**] チェック ボックスをオフにします。既定では、会議の種類が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="2ba12-p108">匿名 (未認証) ユーザーが自動的に承認されないようにするには、[**既定で匿名ユーザーを承認する**] チェック ボックスをオフにします。既定では、匿名ユーザーは会議に対して自動的に承認されます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="2ba12-133">参加者に送られる会議の招待をカスタマイズするには、以下を行います。</span><span class="sxs-lookup"><span data-stu-id="2ba12-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="2ba12-134">URL およびカスタム フッター テキストの長さは最大 1 KB です。</span><span class="sxs-lookup"><span data-stu-id="2ba12-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="2ba12-135">[**ヘルプ URL**] 以外は、カスタムの値を指定しない場合、会議に含まれません。</span><span class="sxs-lookup"><span data-stu-id="2ba12-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="2ba12-136">カスタムヘルプ URL が含まれていない場合は、Lync の既定のヘルプ URL が招待状に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="2ba12-137">会議の招待に表示されるロゴをカスタマイズするには、[**ロゴ URL**] にロゴの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="2ba12-138">ロゴは、サイズが 188 x 30 ピクセルの GIF または JPG 画像である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ba12-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="2ba12-139">会議招待に表示されるヘルプ テキストをカスタマイズするには、[**ヘルプ URL**] にヘルプ テキストの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="2ba12-140">会議の招待に表示される法的情報をカスタマイズするには、[**リーガル テキスト URL**] にロゴの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="2ba12-141">会議の招待に表示されるカスタム フッター テキストをカスタマイズするには、[**カスタム フッターのテキスト**] にテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="2ba12-142">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="2ba12-143">会議構成の既存のコレクションを変更するには</span><span class="sxs-lookup"><span data-stu-id="2ba12-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="2ba12-144">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ba12-145">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ba12-146">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba12-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ba12-147">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="2ba12-148">会議の構成の一覧で、変更する構成をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2ba12-149">[**会議の構成の編集**] で、構成名以外の設定を変更します (構成名は変更不可です)。</span><span class="sxs-lookup"><span data-stu-id="2ba12-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="2ba12-150">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba12-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2ba12-151">Windows PowerShell コマンドレットを使用して新しい会議構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="2ba12-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2ba12-152">会議の構成設定は、Windows PowerShell と新しい-Csの会議構成コマンドレットを使用して、(サイトスコープでのみ) 作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="2ba12-153">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2ba12-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2ba12-154">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba12-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="2ba12-155">既定値を使用する会議構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="2ba12-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="2ba12-156">このコマンドは、Redmond サイト用に会議構成設定の新しいセットを作成しています。</span><span class="sxs-lookup"><span data-stu-id="2ba12-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="2ba12-157">上記のコマンドでは必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい会議構成設定はすべてのプロパティについて既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="2ba12-158">会議構成設定の作成時にプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="2ba12-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="2ba12-p112">異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、会議の全員が発表者となることを既定で許可する会議構成設定のセットを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="2ba12-161">会議の構成設定の作成時に複数のプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="2ba12-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="2ba12-p113">複数のパラメーターを含めることにより複数のプロパティ値を変更できます。たとえば、次のコマンドは、会議の全員が発表者となることを許可し、さらに PSTN ユーザーは会議に対して正式に承認されるまで必ずロビーで待機するように設定しています。</span><span class="sxs-lookup"><span data-stu-id="2ba12-p113">Multiple property values can be modified by including multiple parameters. For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="2ba12-164">詳細につい[ては、](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) 「」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba12-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

