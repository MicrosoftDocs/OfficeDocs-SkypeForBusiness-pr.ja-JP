---
title: 'Lync Server 2013: 音声ルートの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f62b6ba64456b8e892c94117750bf1bc209bc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="b115e-102">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="b115e-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b115e-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b115e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b115e-104">次の手順では、Lync Server 2013 コントロールパネルを使用して、新しい音声ルートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b115e-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="b115e-105">既存のルートを編集するには、手順について「 [Lync Server 2013 で音声ルートを変更](lync-server-2013-modify-a-voice-route.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="b115e-106">Lync Server コントロールパネルを使用して音声ルートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b115e-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b115e-107">RTCUniversalServerAdmins グループのメンバーとして、または**CsVoiceAdministrator**、 **csserveradministrator**、または**csadministrator**管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b115e-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="b115e-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b115e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b115e-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b115e-110">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b115e-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="b115e-111">[**ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b115e-111">Click **Route**.</span></span>

5.  <span data-ttu-id="b115e-112">[**新規**] をクリックして、[**新しい音声ルート**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="b115e-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="b115e-113">[**名前**] に、音声ルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b115e-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="b115e-114">オプション[**説明**] に、音声ルートのわかりやすい追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b115e-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="b115e-115">このルートが対応するパターンを指定するには、[**一致パターンを作成**する] ツールを使用して正規表現を生成するか、手動で正規表現を記述します。</span><span class="sxs-lookup"><span data-stu-id="b115e-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="b115e-p103">**一致パターン構築**ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b115e-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="b115e-118">**許可する番号の先頭の数字:** このルートが対応する必要があるプレフィックス値を入力します (必要に応じて、先頭に + を含めます)。</span><span class="sxs-lookup"><span data-stu-id="b115e-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="b115e-119">たとえば、「 **+ 425**」と入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b115e-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="b115e-120">このルートに含める各プレフィックス値について、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b115e-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="b115e-121">**例外:** プレフィックス値に対して1つ以上の例外を指定する場合は、プレフィックスを強調表示して [**例外**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b115e-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="b115e-122">このルートが対応*しない*一致パターンの値を 1 つまたは複数入力します。</span><span class="sxs-lookup"><span data-stu-id="b115e-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="b115e-123">たとえば、ルートから + 425237 で始まる番号を除外するには、[**例外**] フィールドに **+ 425237**の値を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b115e-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b115e-124">一致パターンを手動で定義するには、**一致パターン構築**ツールの **[編集]** をクリックし、.NET Framework 正規表現を入力して、ルートが適用される相手電話番号の一致パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b115e-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="b115e-125">正規表現の記述方法の詳細については、「」の「.NET [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)Framework の正規表現」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="b115e-p107">通話を発信する電話の ID を呼び出し先に表示しない場合は、**[発信者 ID を表示しない]** を選択します。 このオプションを選択した場合、呼び出し先の発信者 ID 表示に表示される、**[代替発信者 ID]** を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b115e-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="b115e-128">1つまたは複数のトランクを音声ルートに関連付けるには、[**追加**] をクリックして、一覧からトランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="b115e-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b115e-129">展開に Microsoft Office Communications Server 2007 R2 仲介サーバーが含まれている場合は、それらも一覧で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b115e-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="b115e-130">1つまたは複数の公衆交換電話網 (PSTN) の使用法を音声ルートに関連付けるには、[**選択**] をクリックして、エンタープライズ voip 展開に対して定義されている pstn 使用法レコードの一覧からレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b115e-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b115e-131">使用可能な PSTN 使用法レコードの各プロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">VIEW pstn usage records In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="b115e-132">PSTN 使用法レコードを作成または編集するには、「 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">create a voice policy and CONFIGURE pstn usage records In Lync server 2013</A> 」または「 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy」および「configure pstn Usage Records in lync server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="b115e-p108">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b115e-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b115e-135">PSTN 使用法レコードが表示される順序が重要である音声ポリシーとは対照的に、PSTN 使用法レコードが音声ルートに表示される順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b115e-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="b115e-136">ただし、使用頻度でリストを整理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b115e-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="b115e-137">例: RedmondLocal、RedmondLongDist、Redmondlocal、Redmondlocal。</span><span class="sxs-lookup"><span data-stu-id="b115e-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="b115e-138">(Lync Server は、リストを上から下に移動します。)</span><span class="sxs-lookup"><span data-stu-id="b115e-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="b115e-p110">(オプション) **[テストする変換後の番号の入力]** フィールドに値を入力して、**[実行]** をクリックします。 テスト結果がフィールドの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b115e-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b115e-141">まだテストに成功していないボイス ルートを保存して、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b115e-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="b115e-142">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="b115e-143">[ **OK]** をクリックして音声ルートを保存します。</span><span class="sxs-lookup"><span data-stu-id="b115e-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b115e-144">音声ルートを作成するたびに、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b115e-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b115e-145">詳細については、「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 の音声ルーティング構成に対する保留中の変更を公開する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b115e-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b115e-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="b115e-146">See Also</span></span>


[<span data-ttu-id="b115e-147">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="b115e-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="b115e-148">Lync Server 2013 での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="b115e-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="b115e-149">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="b115e-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="b115e-150">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="b115e-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="b115e-151">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="b115e-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="b115e-152">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="b115e-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

