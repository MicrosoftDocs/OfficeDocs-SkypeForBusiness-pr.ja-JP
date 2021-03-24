---
title: Skype for Business でグループ通話ピックアップ番号範囲を作成または変更する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server のグループ通話ピックアップ番号範囲を作成または変更エンタープライズ VoIP。
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100423"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="f6c2f-103">Skype for Business でグループ通話ピックアップ番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f6c2f-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="f6c2f-104">Skype for Business Server のグループ通話ピックアップ番号範囲を作成または変更エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="f6c2f-105">グループ通話ピックアップは、コール パーク アプリケーションに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="f6c2f-106">グループ通話ピックアップを展開する場合は、通話ピックアップ グループ番号として指定された電話番号の範囲でコール パーク オービット テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="f6c2f-107">これらのグループ番号は、ユーザーがダイヤルして別のユーザーの呼び出しを呼び出す番号です。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="f6c2f-108">通話パークオービット番号と同様に、通話ピックアップ グループ番号は、ユーザーまたは電話が割り当てられていない仮想内線番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="f6c2f-109">グループ通話ピックアップを展開する各フロントエンド プールには、1 つ以上の範囲の通話ピックアップ グループ番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="f6c2f-110">グループ番号の範囲は展開でグローバルに一意である必要があります **。GroupPickup の種類として割り当てる必要** があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="f6c2f-111">コール パーク オービット テーブルで通話ピックアップ グループ番号範囲を作成または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="f6c2f-112">Skype for Business Server 管理シェルを使用して、コール パーク オービット テーブルのグループ通話ピックアップ番号範囲を作成、変更、削除、および表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="f6c2f-113">Skype for Business Server コントロール パネルでは、グループ通話ピックアップ番号の範囲を使用できません。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="f6c2f-114">通話ピックアップ グループ番号の範囲は、次のルールに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="f6c2f-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="f6c2f-116">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="f6c2f-p104">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="f6c2f-119">数値範囲が文字または #で始まる場合、範囲は 100 より大きい必要 \* があります。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="f6c2f-120">有効な値: 正規表現文字列と一致する必要があります ([ \\ \*|#]?1-9]\d {0,7} )|([1-9]\d)。 {0,8}</span><span class="sxs-lookup"><span data-stu-id="f6c2f-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="f6c2f-121">つまり、値は、文字または # で始まる文字列か、1 ~ 9 の数値である必要があります (最初の文字は \* 0 にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="f6c2f-122">最初の文字が #の場合、次の文字は 1 ~ 9 の数値 \* である必要があります (ゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="f6c2f-123">後続の文字には、0 ~ 9 の任意の数字 \* ("#6000"、"92000"、"95551212"、"915551212"など) を指定できます。 \*</span><span class="sxs-lookup"><span data-stu-id="f6c2f-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="f6c2f-124">最初の文字が #または #の場合、最初の文字は 1 ~ 9 の数字 (ゼロにすることはできません)、その後に最大 8 文字の数字 (たとえば \* 、"915551212"、"41212"、"300" など) が続きます。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="f6c2f-125">通話ピックアップ グループ範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="f6c2f-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="f6c2f-126">「代理セットアップのアクセス許可」の説明に従って、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="f6c2f-127">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="f6c2f-128">**New-CsCallParkOrbit** を使用して、新しい範囲の通話ピックアップ グループ番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="f6c2f-129">**Set-CsCallParkOrbit** を使用して、通話ピックアップ番号の既存の範囲を変更します。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="f6c2f-130">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="f6c2f-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="f6c2f-132">次の例は、コール パーク オービットから通話ピックアップ グループに番号の範囲を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="f6c2f-133">このコマンドレットを使用して、番号範囲に割り当てられた種類を変更できるのは、最初に正しくない型を指定し、グループ範囲がまだ使用されていない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="f6c2f-134">番号範囲を CallPark から GroupPickup または GroupPickup に変更し、その番号範囲が既に使用されている場合は、コール パークまたはグループ通話ピックアップのどちらかが、その番号範囲で動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="f6c2f-135">たとえば、番号範囲を CallPark から GroupPick に変更した場合、コール パーク アプリケーションでは、その範囲のオービットを使用して呼び出しをパークできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f6c2f-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6c2f-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6c2f-136">See also</span></span>

[<span data-ttu-id="f6c2f-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f6c2f-137">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="f6c2f-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f6c2f-138">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="f6c2f-139">コール パーク オービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="f6c2f-139">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)