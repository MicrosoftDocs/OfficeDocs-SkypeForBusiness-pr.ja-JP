---
title: 'Lync Server 2013: グループ通話の集配番号の範囲を作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="282d3-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="282d3-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="282d3-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="282d3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="282d3-104">次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="282d3-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="282d3-105">通話パークの軌道の番号範囲を作成、変更、削除、および表示するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="282d3-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="282d3-106">グループ通話の集配番号の範囲は Lync Server コントロールパネルでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="282d3-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="282d3-107">通話集配グループの番号範囲には、GroupPickup の種類を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="282d3-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="282d3-108">ユーザーが割り当てられているグループ番号が GroupPickup 型である場合にのみ、グループ通話のピックアップが有効になります。</span><span class="sxs-lookup"><span data-stu-id="282d3-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="282d3-109">通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="282d3-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="282d3-110">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="282d3-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="282d3-111">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="282d3-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="282d3-p103">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="282d3-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="282d3-114">数値の範囲が文字\*で始まる場合、 \#または範囲が100よりも大きい場合。</span><span class="sxs-lookup"><span data-stu-id="282d3-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="282d3-115">有効な値: 正規表現文字列と一致する\[\\\*|\#\]必要\[があります (?1-9\]\\d{0,7}) |(\[1-9\]\\d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="282d3-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="282d3-116">つまり、値は、文字\*また\#は 1 ~ 9 のいずれかの文字列である必要があります (最初の文字をゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="282d3-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="282d3-117">最初の文字が\*または\#である場合、次の文字は 1 ~ 9 の数字である必要があります (ゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="282d3-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="282d3-118">後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば\#、"6000"\*、"92000"\*、"95551212"、"915551212")。</span><span class="sxs-lookup"><span data-stu-id="282d3-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="282d3-119">最初の文字が指定さ\*れ\#ていない場合、または最初の文字が 1 ~ 9 の数字 (0 以外) で、先頭が8文字である必要があります (たとえば、"915551212"、"41212"、"300")。</span><span class="sxs-lookup"><span data-stu-id="282d3-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="282d3-120">通話ピックアップ グループの範囲を作成するには</span><span class="sxs-lookup"><span data-stu-id="282d3-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="282d3-121">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="282d3-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="282d3-122">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="282d3-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="282d3-123">通話ピックアップ グループ番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="282d3-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="282d3-124">通話ピックアップ番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="282d3-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="282d3-125">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="282d3-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="282d3-126">例:</span><span class="sxs-lookup"><span data-stu-id="282d3-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="282d3-127">次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="282d3-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="282d3-128">最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。</span><span class="sxs-lookup"><span data-stu-id="282d3-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="282d3-129">番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="282d3-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="282d3-130">たとえば、番号の範囲を [CallPark] から [GroupPick] に変更すると、その範囲の orbits を使用して通話をパークすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="282d3-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="282d3-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="282d3-131">See Also</span></span>


[<span data-ttu-id="282d3-132">Lync Server 2013 でのコールパークの範囲の削除</span><span class="sxs-lookup"><span data-stu-id="282d3-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="282d3-133">新規-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="282d3-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="282d3-134">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="282d3-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

