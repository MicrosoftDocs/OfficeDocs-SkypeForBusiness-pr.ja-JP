---
title: 'Lync Server 2013: 割り当てられていない番号範囲を作成または変更する'
description: 'Lync Server 2013: 割り当てられていない番号範囲を作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2998616b931e94c9c38fc44d569b84b3af37709d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546953"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="2dbb8-103">Lync Server 2013 で割り当てられていない番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2dbb8-103">Create or modify an unassigned number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dbb8-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2dbb8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2dbb8-105">アナウンスアプリケーションに割り当てられていない番号範囲を構成するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-105">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2dbb8-106">割り当てられていない番号の表を構成する前に、既に1つ以上のアナウンスを定義しているか、Exchange ユニファイドメッセージング (UM) 自動応答を設定している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-106">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="2dbb8-107">Lync Server コントロールパネルを使用して割り当てられていない電話番号を構成するには</span><span class="sxs-lookup"><span data-stu-id="2dbb8-107">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="2dbb8-108">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2dbb8-109">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2dbb8-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2dbb8-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2dbb8-112">左側のナビゲーションバーで [ **音声機能**] をクリックし、[割り当てられていない **番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-112">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="2dbb8-113">[割り当てられていない **番号** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-113">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2dbb8-114">新しい番号範囲を作成するには、[ **新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-114">To create a new number range, click **New**.</span></span> <span data-ttu-id="2dbb8-115">[**名前**] に、この番号範囲の識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-115">In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2dbb8-116">新しい割り当てられていない番号範囲をデータベースにコミットした後に、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-116">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="2dbb8-117">既存の番号範囲を変更するには、検索フィールドに番号範囲の名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-117">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="2dbb8-118">結果の番号範囲の一覧で、必要な名前をクリックし、[ **編集**] をクリックして、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-118">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2dbb8-119">最初の **[数値の範囲]** フィールドに範囲の開始番号を入力し、2 番目の **[数値の範囲]** フィールドに範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-119">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="2dbb8-120">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-120">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2dbb8-121">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-121">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2dbb8-122">数値は正規表現 (tel:)? () と一致する必要があり \+ ますか?[1-9] \d {0,17} (; ext = [1-9] \d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="2dbb8-122">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="2dbb8-123">これは、数値が文字列 tel: (文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、数字 1 ~ 9 で始まることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-123">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="2dbb8-124">電話番号は最大17桁にすることができ、その後に形式で内線番号を続け、内線番号を続けて指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-124">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="2dbb8-125">**[アナウンス サービス]** で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-125">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="2dbb8-126">**[アナウンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-126">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="2dbb8-127">**[Exchange UM]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-127">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="2dbb8-128">前の手順で **[アナウンス]** をクリックした場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-128">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="2dbb8-129">**[宛先サーバーの FQDN]** で、**[選択]** をクリックし、この割り当てられていない番号範囲への着信通話を処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-129">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="2dbb8-130">**[アナウンス]** で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-130">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="2dbb8-131">前の手順で **[Exchange UM]** をクリックした場合は、**[自動応答の電話番号]** で、**[選択]** をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-131">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="2dbb8-132">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-132">Click **OK**.</span></span>

10. <span data-ttu-id="2dbb8-133">[割り当てられていない **番号** ] ページで、割り当てられていない番号範囲が目的の順序で並んでいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-133">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="2dbb8-134">表の範囲の位置を変更するには、範囲の一覧で1つ以上の連続する名前をクリックし、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-134">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2dbb8-135">Lync Server は、割り当てられていない番号の表を上から下へ検索し、割り当てられていない番号に一致する最初の範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-135">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="2dbb8-136">重複する範囲があり、1つの範囲が最後のリゾートアクションを指定している場合は、その範囲がリストの一番下にあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-136">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="2dbb8-137">割り当てられていない番号範囲が目的の順序で表示されている場合は、[ **すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-137">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="2dbb8-138">Windows PowerShell を使用して割り当てられていない電話番号を構成するには</span><span class="sxs-lookup"><span data-stu-id="2dbb8-138">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="2dbb8-139">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-139">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2dbb8-140">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2dbb8-141">新しい未使用の番号範囲を作成するには **、remove-csunassignednumber** を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-141">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="2dbb8-142">既存の割り当てられていない番号範囲を変更するには、 **remove-csunassignednumber** を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-142">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2dbb8-143">重複する範囲があり、範囲が特定の順序で適用されるようにする場合は、Priority パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-143">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="2dbb8-144">優先度の高い範囲が通話に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-144">The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="2dbb8-145">コマンドラインで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-145">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="2dbb8-146">アナウンスサービスの番号範囲を作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-146">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="2dbb8-147">または、Exchange UM 自動応答の番号範囲を作成するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-147">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="2dbb8-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-148">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="2dbb8-149">または</span><span class="sxs-lookup"><span data-stu-id="2dbb8-149">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="2dbb8-150">次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-150">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2dbb8-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dbb8-151">See Also</span></span>


[<span data-ttu-id="2dbb8-152">Lync Server 2013 で割り当てられていない番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="2dbb8-152">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="2dbb8-153">Remove-csunassignednumber</span><span class="sxs-lookup"><span data-stu-id="2dbb8-153">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="2dbb8-154">Remove-csunassignednumber</span><span class="sxs-lookup"><span data-stu-id="2dbb8-154">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="2dbb8-155">Remove-csunassignednumber</span><span class="sxs-lookup"><span data-stu-id="2dbb8-155">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

