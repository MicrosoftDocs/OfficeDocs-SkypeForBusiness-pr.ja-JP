---
title: 作成またはビジネス用の Skype のコール ピックアップのグループ番号の範囲を変更します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype のコール ピックアップのグループ番号の範囲を変更します。
ms.openlocfilehash: 15906402fe81047f02fc033ba7a051a4169a0f26
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002454"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="3f663-103">作成またはビジネス用の Skype のコール ピックアップのグループ番号の範囲を変更します。</span><span class="sxs-lookup"><span data-stu-id="3f663-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>
 
<span data-ttu-id="3f663-104">作成またはビジネス サーバーのエンタープライズ VoIP の Skype のコール ピックアップのグループ番号の範囲を変更します。</span><span class="sxs-lookup"><span data-stu-id="3f663-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3f663-105">グループ コール ピックアップは、コール パーク アプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="3f663-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="3f663-106">コール ピックアップのグループを配置するときは、コール ピックアップ グループの番号として指定されている電話番号の範囲のコール パークの移動テーブルを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3f663-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="3f663-107">ユーザーはこのグループ番号にダイヤルし、他のユーザーに着信している通話をピックアップします。</span><span class="sxs-lookup"><span data-stu-id="3f663-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>
  
<span data-ttu-id="3f663-108">コール パーク オービットの番号と同様に、通話ピックアップのグループ番号には、ユーザーや電話が割り当てられていない仮想の内線番号を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f663-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="3f663-109">コール ピックアップのグループを展開する各フロント エンド プールでは、コール ピックアップ グループ番号の 1 つまたは複数の範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="3f663-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="3f663-110">このグループ番号範囲は、展開全体でグローバルに一意である必要があり、**GroupPickup** の種類として割り当てることも必要です。</span><span class="sxs-lookup"><span data-stu-id="3f663-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>
  
<span data-ttu-id="3f663-111">次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="3f663-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3f663-112">作成、変更、削除、および呼び出し公園軌道テーブルのグループを呼び出すピックアップの数値の範囲を表示するビジネス サーバー管理シェルの Skype を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3f663-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="3f663-113">グループ ピックアップの電話番号の範囲は、ビジネス サーバーのコントロール パネルの Skype でご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="3f663-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="3f663-114">通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f663-114">The call pickup group number ranges must comply with the following rules:</span></span>
  
- <span data-ttu-id="3f663-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3f663-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
- <span data-ttu-id="3f663-116">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f663-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
- <span data-ttu-id="3f663-p104">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3f663-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
- <span data-ttu-id="3f663-119">番号の範囲が、文字で始まる場合\*#、範囲は 100 より大きい値である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="3f663-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
- <span data-ttu-id="3f663-120">有効な値: 正規表現の文字列に一致する必要があります ([\\* | #] ? [1-9] \d{0,7})。(1 ~ 9 の \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="3f663-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="3f663-121">つまり、値は、いずれかの文字で始まる文字列である必要があります\*#、または数字 1 ~ 9 の (最初の文字はゼロであることはできません)。</span><span class="sxs-lookup"><span data-stu-id="3f663-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="3f663-122">最初の文字の場合\*#、次の文字は数字 1 ~ 9 の (0 にすることはできません) である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="3f663-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="3f663-123">以降の文字は、任意の数の 0 から 9 までの 7 つの追加文字を使用できます (たとえば、「#6000」、「\*92000"、"\*95551212"、および"915551212").</span><span class="sxs-lookup"><span data-stu-id="3f663-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="3f663-124">最初の文字がない場合\*#、最初の文字は、最大 8 個までの文字の後に数字 1 ~ 9 (0 にすることはできません) である必要がありますまたは各数値 0 から 9 (たとえば、「915551212」、「41212」、「300」)。</span><span class="sxs-lookup"><span data-stu-id="3f663-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="3f663-125">通話ピックアップ グループの範囲を作成するには</span><span class="sxs-lookup"><span data-stu-id="3f663-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="3f663-126">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3f663-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="3f663-127">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f663-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3f663-128">コール ピックアップ グループ番号の新しい範囲を作成するのにには、**新しい CsCallParkOrbit**を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f663-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="3f663-129">**セット CsCallParkOrbit**を使用すると、コール ピックアップ番号の既存の範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3f663-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="3f663-130">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f663-130">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="3f663-131">例:</span><span class="sxs-lookup"><span data-stu-id="3f663-131">For example:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="3f663-132">次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f663-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="3f663-133">最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。</span><span class="sxs-lookup"><span data-stu-id="3f663-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="3f663-134">番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。</span><span class="sxs-lookup"><span data-stu-id="3f663-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="3f663-135">たとえば、番号の範囲を CallPark から GroupPick に変更する場合は、コール パーク アプリケーションことができます公園の呼び出しに軌道の範囲は使用できません。</span><span class="sxs-lookup"><span data-stu-id="3f663-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3f663-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f663-136">See also</span></span>

[<span data-ttu-id="3f663-137">新しい-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="3f663-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="3f663-138">セット CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="3f663-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="3f663-139">コール パークの移動範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="3f663-139">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)