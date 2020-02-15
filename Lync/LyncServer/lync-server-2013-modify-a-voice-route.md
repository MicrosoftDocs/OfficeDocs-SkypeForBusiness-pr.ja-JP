---
title: 'Lync Server 2013: 音声ルートの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86c64b9cc595c108676a519bc98cba3ecad04a62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="757d7-102">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="757d7-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="757d7-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="757d7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="757d7-104">ここでは、ボイス ルートを編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="757d7-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="757d7-105">新しいルートを作成するには、「 [Lync Server 2013 で音声ルートを作成](lync-server-2013-create-a-voice-route.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="757d7-106">ボイス ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="757d7-106">To modify a voice route</span></span>

1.  <span data-ttu-id="757d7-107">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="757d7-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="757d7-108">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="757d7-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="757d7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="757d7-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="757d7-111">左側のナビゲーション バーで [**音声ルート**] をクリックし、[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="757d7-112">**[ルート]** ページで、次のいずれかの方法を使用してボイス ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="757d7-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="757d7-113">ボイス ルート名をクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="757d7-p104">ボイス ルート名をクリックし、**[編集]** をクリックし、**[コピー]** をクリックしてから、**[貼り付け]** をクリックします。 直前に作成したボイス ルートの新しいコピーをクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="757d7-116">**[ボイス ルートの編集]** ページの **[名前]** フィールドに、ボイス ルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="757d7-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="757d7-117">(オプション) **[説明]** フィールドに、ボイス ルートのわかりやすい追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="757d7-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="757d7-118">このルートが対応するパターンを指定するには、**一致パターン構築**ツールを使用して正規表現を生成するか、手動で正規表現を記述します。</span><span class="sxs-lookup"><span data-stu-id="757d7-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="757d7-p105">**一致パターン構築**ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="757d7-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="757d7-121">**許可する番号の先頭の数字:** このルートが対応する必要があるプレフィックス値を入力します (必要に応じて、先頭に + を含めます)。</span><span class="sxs-lookup"><span data-stu-id="757d7-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="757d7-122">たとえば、「**+425**」と入力して、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="757d7-123">このルートに含める各プレフィックス値について、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="757d7-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="757d7-124">**例外:** プレフィックス値に対して1つ以上の例外を指定する場合は、プレフィックスを強調表示して [**例外**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="757d7-125">このルートが対応*しない*一致パターンの値を 1 つまたは複数入力します。</span><span class="sxs-lookup"><span data-stu-id="757d7-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="757d7-126">たとえば、ルートから + 425237 で始まる番号を除外するには、[**例外**] フィールドに **+ 425237**の値を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="757d7-127">一致パターンを手動で定義するには、**一致パターン構築**ツールの **[編集]** をクリックし、.NET Framework 正規表現を入力して、ルートが適用される相手電話番号の一致パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="757d7-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="757d7-128">正規表現を記述する方法については、「」の「.NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)正規表現」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="757d7-129">発信通話を発信する電話の ID を呼び出し先に表示しない場合は、[**発信者 id の非**表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="757d7-129">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="757d7-130">このオプションを選択した場合、呼び出し先の発信者 ID 表示に表示される、**[代替発信者 ID]** を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="757d7-130">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="757d7-131">1つまたは複数の公衆交換電話網 (PSTN) トランクを音声ルートに関連付けるには、[**追加**] をクリックして、一覧からトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="757d7-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="757d7-132">展開に Microsoft Office Communications Server 2007 R2 仲介サーバーが含まれている場合は、それらも一覧で利用できます。</span><span class="sxs-lookup"><span data-stu-id="757d7-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="757d7-133">1つまたは複数の PSTN 使用法を音声ルートに関連付けるには、[**選択**] をクリックして、エンタープライズ voip 展開に対して定義されている pstn 使用法レコードの一覧からレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="757d7-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="757d7-134">使用可能な PSTN 使用法レコードの各プロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">VIEW pstn usage records In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="757d7-135">PSTN 使用法レコードを作成または編集するには、「 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">create a voice policy and CONFIGURE pstn usage records In Lync server 2013</A> 」または「 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy」および「configure pstn Usage Records in lync server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="757d7-p110">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="757d7-138">PSTN 使用法レコードが表示される順序が重要であるという点では、ボイスルートでの PSTN 使用法レコードの順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="757d7-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="757d7-139">ただし、リストを使用頻度で整理することをお勧めします。例: RedmondLocal、RedmondLongDist、Redmondlocal、Redmondlocal。</span><span class="sxs-lookup"><span data-stu-id="757d7-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="757d7-140">(Lync Server は、リストを上から下に移動します。)</span><span class="sxs-lookup"><span data-stu-id="757d7-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="757d7-p112">(オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="757d7-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="757d7-143">まだテストに成功していないボイス ルートを保存して、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="757d7-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="757d7-144">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="757d7-145">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-145">Click **OK**.</span></span>

14. <span data-ttu-id="757d7-146">**[ルート]** ページの **[確定]** をクリックして、**[すべて確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="757d7-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="757d7-147">音声ルートを作成または変更するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="757d7-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="757d7-148">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="757d7-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="757d7-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="757d7-149">See Also</span></span>


[<span data-ttu-id="757d7-150">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="757d7-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="757d7-151">Lync Server 2013 での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="757d7-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="757d7-152">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="757d7-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="757d7-153">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="757d7-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="757d7-154">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="757d7-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="757d7-155">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="757d7-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

