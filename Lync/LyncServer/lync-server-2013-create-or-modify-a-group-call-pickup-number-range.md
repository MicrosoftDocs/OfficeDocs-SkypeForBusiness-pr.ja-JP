---
title: 'Lync Server 2013: グループ通話ピックアップ番号の範囲の作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd323e609a811a9735c966645c5176fb8784bb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="26397-102">Lync Server 2013 でグループ通話ピックアップ番号の範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="26397-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26397-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="26397-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="26397-104">次の手順を使用して、コールパークオービットテーブルで通話ピックアップグループの番号範囲を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="26397-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26397-105">通話パークオービットテーブルでグループ通話ピックアップ番号の範囲を作成、変更、削除、表示するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26397-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="26397-106">グループ通話ピックアップ番号の範囲は、Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="26397-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="26397-107">通話ピックアップグループ番号の範囲には、GroupPickup の種類を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="26397-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="26397-108">ユーザーが割り当てられているグループ番号が GroupPickup の場合にのみ、グループ通話ピックアップが有効になります。</span><span class="sxs-lookup"><span data-stu-id="26397-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="26397-109">通話ピックアップグループ番号の範囲は、次のルールに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="26397-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="26397-110">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="26397-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="26397-111">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="26397-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="26397-p103">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="26397-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="26397-114">番号範囲が文字\*または\#で始まる場合、範囲は100より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="26397-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="26397-115">有効な値: 正規表現文字列である必要\[\\\*|\#\]が\[あります (?1-9\]\\d{0,7}) |(\[1-9\]\\d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="26397-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="26397-116">つまり、値は、文字\*また\#は 1 ~ 9 の数字で始まる文字列である必要があります (最初の文字を0にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="26397-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="26397-117">最初の文字が\*または\#の場合、次の文字は 1 ~ 9 の数字である必要があります (ゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="26397-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="26397-118">後続の文字には、0から9までの任意の文字を追加できます (\#たとえば、"6000\*"、"92000\*"、"95551212"、"915551212" など)。</span><span class="sxs-lookup"><span data-stu-id="26397-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="26397-119">最初の文字がまたは\*で\#はない場合、最初の文字は 1 ~ 9 の数字 (0 にはできません)、数字 0 ~ 9 (例: "915551212"、"41212"、"300") のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="26397-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="26397-120">通話ピックアップグループの範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="26397-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="26397-121">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="26397-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="26397-122">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="26397-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26397-123">新しい通話ピックアップグループ番号の範囲を作成するには、 **get-cscallparkorbit**を使用します。</span><span class="sxs-lookup"><span data-stu-id="26397-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="26397-124">通話ピックアップ番号の既存の範囲を変更するには、 **get-cscallparkorbit**を使用します。</span><span class="sxs-lookup"><span data-stu-id="26397-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="26397-125">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="26397-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="26397-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26397-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="26397-127">次の例は、電話パークオービットからピックアップグループを呼び出すために番号の範囲を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="26397-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="26397-128">番号範囲に割り当てられる種類を変更するには、最初に間違った種類を指定し、グループ範囲がまだ使用されていない場合にのみ、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="26397-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="26397-129">番号範囲を CallPark から GroupPickup に変更した場合や、番号範囲が既に使用されている場合は、コールパークまたはグループ通話ピックアップのいずれかがその番号範囲に対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="26397-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="26397-130">たとえば、番号の範囲を CallPark から GroupPick に変更した場合、コールパークアプリケーションはその範囲のオービットを使用して通話をパークすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="26397-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26397-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="26397-131">See Also</span></span>


[<span data-ttu-id="26397-132">Lync Server 2013 でのコールパークオービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="26397-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="26397-133">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="26397-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="26397-134">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="26397-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

