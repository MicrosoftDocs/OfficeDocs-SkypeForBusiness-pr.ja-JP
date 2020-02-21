---
title: 'Lync Server 2013: コールパークオービット範囲の作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fe04aea0cc0d6ab38b0bfa9597b420d608c7597
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="a636d-102">Lync Server 2013 でのコールパークオービット範囲の作成または変更</span><span class="sxs-lookup"><span data-stu-id="a636d-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a636d-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a636d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a636d-104">コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a636d-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="a636d-105">Lync Server コントロールパネルを使用して、保留呼び出しの番号範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="a636d-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="a636d-106">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a636d-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a636d-107">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a636d-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a636d-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a636d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a636d-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a636d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a636d-110">左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a636d-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="a636d-111">[**コール パーク**] ページで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="a636d-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a636d-p103">新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a636d-p103">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a636d-114">オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a636d-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="a636d-p104">既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a636d-p104">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a636d-117">最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="a636d-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="a636d-118">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a636d-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a636d-119">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a636d-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a636d-p105">オービット範囲は一意である必要があります。 この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a636d-p105">The orbit range must be unique. This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a636d-122">オービット範囲が、文字 \* または # で始まる場合、範囲は 100 を超える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a636d-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a636d-123">有効な値: 正規表現文字列と一致する必要\*があります ([| #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="a636d-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="a636d-124">つまり、値には \* または # の文字あるいは 1 ～ 9 の数字で始まる文字列を指定する必要があります (最初の文字を 0 にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="a636d-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="a636d-125">最初の文字が \* または # である場合、次の文字には 1 ～ 9 の数字 (0 は不可) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a636d-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="a636d-126">後続の文字には、0から9までの任意の文字を追加できます (たとえば、"#6000"、"*92000"、*"95551212"、"915551212" など)。</span><span class="sxs-lookup"><span data-stu-id="a636d-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="a636d-127">最初の文字が \* または # ではない場合、最初の文字には 1 ～ 9 の数字 (0 は不可) を指定し、その後に 0 ～ 9 の数字を最大 8 文字まで指定します ("915551212"、"41212"、"300" など)。</span><span class="sxs-lookup"><span data-stu-id="a636d-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a636d-p107">プール当たりの合計が 50,000 オービットを超えないようにしてください。 各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。 たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a636d-p107">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="a636d-p108">**[宛先サーバーの FQDN]** で、コール パーク アプリケーションをホストするアプリケーション サービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。 オービット範囲の開始番号と終了番号で指定された範囲の番号にパークされるすべての通話は、このサーバーまたはプールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="a636d-p108">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="a636d-133">**[確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a636d-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="a636d-134">Windows PowerShell を使用して、保留呼び出しの番号範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="a636d-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="a636d-135">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="a636d-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a636d-136">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a636d-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a636d-137">オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="a636d-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="a636d-138">オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="a636d-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="a636d-139">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a636d-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="a636d-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a636d-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="a636d-141">次の例は、既存のオービット範囲内の番号を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a636d-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a636d-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a636d-142">See Also</span></span>


[<span data-ttu-id="a636d-143">Lync Server 2013 でのコールパークオービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="a636d-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="a636d-144">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="a636d-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="a636d-145">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="a636d-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

