---
title: Skype for Business のグループ通話集配の番号範囲を作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Skype for Business Server Enterprise Voice でグループ通話の集配番号の範囲を作成または変更します。
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767880"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="db5d7-103">Skype for Business のグループ通話集配の番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="db5d7-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="db5d7-104">Skype for Business Server Enterprise Voice でグループ通話の集配番号の範囲を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="db5d7-105">グループ通話のピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="db5d7-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="db5d7-106">グループ通話の集配を展開するときに、通話集配グループ番号として指定されている電話番号の範囲を使って、コールパークの軌道テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="db5d7-107">ユーザーはこのグループ番号にダイヤルし、他のユーザーに着信している通話をピックアップします。</span><span class="sxs-lookup"><span data-stu-id="db5d7-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="db5d7-108">コール パーク オービットの番号と同様に、通話ピックアップのグループ番号には、ユーザーや電話が割り当てられていない仮想の内線番号を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="db5d7-109">グループ通話のピックアップを展開する各フロントエンドプールには、1つ以上の通話ピックアップグループ番号が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="db5d7-110">このグループ番号範囲は、展開全体でグローバルに一意である必要があり、**GroupPickup** の種類として割り当てることも必要です。</span><span class="sxs-lookup"><span data-stu-id="db5d7-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="db5d7-111">次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="db5d7-112">通話パークの軌道の番号範囲を作成、変更、削除、および表示するには、Skype for Business Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="db5d7-113">グループ通話の集配番号範囲は、Skype for Business Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="db5d7-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="db5d7-114">通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="db5d7-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="db5d7-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="db5d7-116">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="db5d7-p104">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="db5d7-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="db5d7-119">数値の範囲が文字\*または # で始まる場合、範囲は100よりも大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="db5d7-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="db5d7-120">有効な値: 正規表現文字列と一致する必要\\があります ([\* | #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8})</span><span class="sxs-lookup"><span data-stu-id="db5d7-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="db5d7-121">つまり、文字\*または # のいずれかから始まる文字列、または 1 ~ 9 の数値 (最初の文字はゼロにすることはできません) であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="db5d7-122">最初の文字が\*または # の場合、次の文字は 1 ~ 9 の数字にする必要があります (0 にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="db5d7-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="db5d7-123">後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば、"#6000"\*、"92000"\*、"95551212"、"915551212")。</span><span class="sxs-lookup"><span data-stu-id="db5d7-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="db5d7-124">最初の文字が "not \* " または "#" である場合、最初の文字は 1 ~ 9 の数字 (0 にすることはできません)、数字 0 ~ 9 (たとえば、"915551212"、"41212"、"300") でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="db5d7-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="db5d7-125">通話ピックアップ グループの範囲を作成するには</span><span class="sxs-lookup"><span data-stu-id="db5d7-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="db5d7-126">Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="db5d7-127">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="db5d7-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="db5d7-128">通話ピックアップ グループ番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="db5d7-129">通話ピックアップ番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="db5d7-130">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="db5d7-131">例:</span><span class="sxs-lookup"><span data-stu-id="db5d7-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="db5d7-132">次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="db5d7-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="db5d7-133">最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。</span><span class="sxs-lookup"><span data-stu-id="db5d7-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="db5d7-134">番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="db5d7-135">たとえば、番号の範囲を [CallPark] から [GroupPick] に変更すると、その範囲の orbits を使用して通話をパークすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="db5d7-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="db5d7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="db5d7-136">See also</span></span>

[<span data-ttu-id="db5d7-137">新規-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="db5d7-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="db5d7-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="db5d7-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="db5d7-139">コールパークの範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="db5d7-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
