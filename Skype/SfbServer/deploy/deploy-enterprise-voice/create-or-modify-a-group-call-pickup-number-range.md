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
description: Create or modify a Group Call Pickup number range in Skype for Business Server エンタープライズ VoIP.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822407"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="00234-103">Skype for Business でグループ通話ピックアップ番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="00234-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="00234-104">Create or modify a Group Call Pickup number range in Skype for Business Server エンタープライズ VoIP.</span><span class="sxs-lookup"><span data-stu-id="00234-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="00234-105">グループ通話ピックアップはコール パーク アプリケーションに基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="00234-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="00234-106">グループ通話ピックアップを展開する場合は、通話ピックアップ グループ番号として指定された電話番号の範囲でコール パーク オービット テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="00234-107">これらのグループ番号は、別のユーザーに呼び出し音を鳴らしている通話を受け取るユーザーがダイヤルする番号です。</span><span class="sxs-lookup"><span data-stu-id="00234-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="00234-108">コール パーク オービット番号と同様に、通話ピックアップ グループ番号は、ユーザーまたは電話が割り当てられていない仮想内線番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="00234-109">グループ通話ピックアップを展開する各フロントエンド プールには、1 つ以上の通話ピックアップ グループ番号の範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="00234-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="00234-110">グループ番号の範囲は、展開内でグローバルに一意である必要があります **。GroupPickup の種類として割り当てる必要** があります。</span><span class="sxs-lookup"><span data-stu-id="00234-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="00234-111">コール パーク オービット テーブル内の通話ピックアップ グループ番号範囲を作成または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="00234-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="00234-112">Skype for Business Server 管理シェルを使用して、コール パーク オービット テーブル内のグループ通話ピックアップ番号範囲を作成、変更、削除、および表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="00234-113">グループ通話ピックアップ番号の範囲は、Skype for Business Server コントロール パネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="00234-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="00234-114">通話ピックアップ グループ番号の範囲は、次のルールに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="00234-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="00234-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="00234-116">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="00234-p104">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="00234-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="00234-119">番号範囲が文字または #で始まる場合、範囲は \* 100 より大きい必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="00234-120">有効な値: 正規表現文字列 ([ \\ \*|#]?[1-9]\d {0,7} )|([1-9]\d {0,8} )。</span><span class="sxs-lookup"><span data-stu-id="00234-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="00234-121">つまり、値は、文字または # で始まる文字列、または 1 ~ 9 の数字 (最初の文字は \* 0 にすることはできません) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="00234-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="00234-122">最初の文字が #または #の場合、次の文字は 1 ~ \* 9 の数値である必要があります (ゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="00234-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="00234-123">後続の文字には、0 ~ 9 の任意の数字を指定できます (たとえば \* 、"#6000"、"92000"、"95551212"、"915551212")。 \*</span><span class="sxs-lookup"><span data-stu-id="00234-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="00234-124">最初の文字がそれ以外または #の場合、最初の文字は 1 ~ 9 の数値 (ゼロにすることはできません)、0 ~ 9 の最大 8 文字を指定する必要があります \* (たとえば、"915551212"、"41212"、"300")。</span><span class="sxs-lookup"><span data-stu-id="00234-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="00234-125">通話ピックアップ グループの範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="00234-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="00234-126">Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**</span><span class="sxs-lookup"><span data-stu-id="00234-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="00234-127">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00234-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="00234-128">**New-CsCallParkOrbit** を使用して、通話ピックアップ グループ番号の新しい範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="00234-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="00234-129">**Set-CsCallParkOrbit** を使用して、通話ピックアップ番号の既存の範囲を変更します。</span><span class="sxs-lookup"><span data-stu-id="00234-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="00234-130">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="00234-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="00234-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="00234-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="00234-132">次の例は、コール パーク オービットから通話ピックアップ グループに番号の範囲を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="00234-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="00234-133">このコマンドレットを使用して番号範囲に割り当てられた種類を変更できるのは、最初に正しくない種類を指定したが、グループ範囲がまだ使用されていない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="00234-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="00234-134">番号範囲を CallPark から GroupPickup に変更した場合、またはその逆に番号範囲が既に使用されている場合は、コール パークまたはグループ通話ピックアップのどちらかが、その番号範囲で機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="00234-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="00234-135">たとえば、番号範囲を CallPark から GroupPick に変更すると、コール パーク アプリケーションは、その範囲のオービットを使用して通話をパークできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="00234-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="00234-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="00234-136">See also</span></span>

[<span data-ttu-id="00234-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="00234-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="00234-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="00234-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="00234-139">コール パーク オービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="00234-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
