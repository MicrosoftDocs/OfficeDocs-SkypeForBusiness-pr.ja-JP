---
title: 作成またはビジネス用の Skype でコール パークの移動範囲を変更します。
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype では、コール パーク軌道範囲テーブルを変更します。
ms.openlocfilehash: ccbde7291a97e834aade35fb62dc074064f9d58c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009733"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="7aed5-103">作成またはビジネス用の Skype でコール パークの移動範囲を変更します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-103">Create or modify a Call Park orbit range in Skype for Business</span></span>
 
<span data-ttu-id="7aed5-104">作成またはビジネス サーバーのエンタープライズ VoIP の Skype では、コール パーク軌道範囲テーブルを変更します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7aed5-105">パークでは、呼び出しを駐車場の軌道を使用します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="7aed5-106">ユーザーは駐車し、呼び出しを取得する前に、コール パーク軌道テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aed5-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="7aed5-107">パーク プール処理のそれぞれの範囲を指定することで内線番号 (軌道) を組織は呼び出しを駐車場の予約し、これらの範囲のルーティングを定義の範囲を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aed5-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="7aed5-108">軌道の範囲を定義するときでは、1 つの軌道がいないため、多くの軌道が拡張機能をユーザーが使用できるその他のサービスの数を制限することが早すぎる、再利用しないように十分な軌道にします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="7aed5-109">コール パーク アプリケーションが展開されているビジネス サーバー プールの各 Skype の複数のコール パークの移動範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="7aed5-110">各コール パークの移動範囲には、グローバルに一意の名前と拡張子の一意のセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="7aed5-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7aed5-p102">一般的にオービット範囲には 100 未満のオービットが含まれます。1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="7aed5-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span> 
  
<span data-ttu-id="7aed5-114">オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7aed5-115">コール パークの回り込みの数値と直接向きダイヤル (DID) 番号を割り当てることの移動テーブルはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7aed5-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span> 
  
<span data-ttu-id="7aed5-116">コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-116">Use one of the following procedures to create or modify a call park orbit range.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="7aed5-117">作成または呼び出しを駐車場の番号の範囲を変更するビジネス サーバーのコントロール パネルの Skype を使用するには</span><span class="sxs-lookup"><span data-stu-id="7aed5-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="7aed5-118">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7aed5-119">詳細については、**セットアップのアクセス許可の委任**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aed5-119">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7aed5-120">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7aed5-121">左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>
    
4. <span data-ttu-id="7aed5-122">[**コール パーク**] ページで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-122">On the **Call Park** page, do one of the following:</span></span>
    
  - <span data-ttu-id="7aed5-p104">新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7aed5-125">オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7aed5-125">After you commit the orbit range to the database, you cannot change this name.</span></span> 
  
  - <span data-ttu-id="7aed5-p105">既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7aed5-128">最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="7aed5-129">あります。</span><span class="sxs-lookup"><span data-stu-id="7aed5-129">Be aware:</span></span>
    
   - <span data-ttu-id="7aed5-130">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7aed5-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="7aed5-131">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aed5-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
   - <span data-ttu-id="7aed5-p107">オービット範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7aed5-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>
    
   - <span data-ttu-id="7aed5-134">軌道の範囲の文字で始まる場合\*#、範囲は 100 より大きい値である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="7aed5-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>
    
   - <span data-ttu-id="7aed5-135">有効な値: 正規表現の文字列に一致する必要があります ([\\* | #] ? [1-9] \d{0,7})。(1 ~ 9 の \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="7aed5-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="7aed5-136">つまり、値は、いずれかの文字で始まる文字列である必要があります\*#、または数字 1 ~ 9 の (最初の文字はゼロであることはできません)。</span><span class="sxs-lookup"><span data-stu-id="7aed5-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="7aed5-137">最初の文字の場合\*#、次の文字は数字 1 ~ 9 の (0 にすることはできません) である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="7aed5-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="7aed5-138">以降の文字は、任意の数の 0 から 9 までの 7 つの追加文字を使用できます (たとえば、「#6000」、「\*92000"、"\*95551212"、および"915551212").</span><span class="sxs-lookup"><span data-stu-id="7aed5-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="7aed5-139">最初の文字がない場合\*#、最初の文字は、最大 8 個までの文字の後に数字 1 ~ 9 (0 にすることはできません) である必要がありますまたは各数値 0 から 9 (たとえば、「915551212」、「41212」、「300」)。</span><span class="sxs-lookup"><span data-stu-id="7aed5-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
   - <span data-ttu-id="7aed5-p109">プール当たりの合計が 50,000 オービットを超えないようにしてください。各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7aed5-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
6. <span data-ttu-id="7aed5-143">**移行先サーバーの FQDN**、完全修飾ドメイン名 (FQDN) をクリックするか、コール パーク アプリケーションをホストするアプリケーション サービスの ID をサービスします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="7aed5-144">オービット範囲の開始番号と終了番号で指定された範囲内の番号にパークされる通話は、すべてこのサーバーまたはプールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="7aed5-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>
    
7. <span data-ttu-id="7aed5-145">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-145">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="7aed5-146">作成または呼び出しを駐車場の番号の範囲を変更する Skype ビジネス サーバー管理シェルを使用するには</span><span class="sxs-lookup"><span data-stu-id="7aed5-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="7aed5-147">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="7aed5-148">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aed5-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7aed5-149">軌道番号の新しい範囲を作成するのにには、**新しい CsCallParkOrbit**を使用します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="7aed5-150">**セット CsCallParkOrbit**を使用すると、回り込み番号の既存の範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7aed5-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="7aed5-151">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-151">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="7aed5-152">例:</span><span class="sxs-lookup"><span data-stu-id="7aed5-152">For example:</span></span>
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="7aed5-153">次の例は、既存のオービット範囲内の番号を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7aed5-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="7aed5-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aed5-154">See also</span></span>

[<span data-ttu-id="7aed5-155">新しい-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="7aed5-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="7aed5-156">セット CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="7aed5-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="7aed5-157">コール パークの移動範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="7aed5-157">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)