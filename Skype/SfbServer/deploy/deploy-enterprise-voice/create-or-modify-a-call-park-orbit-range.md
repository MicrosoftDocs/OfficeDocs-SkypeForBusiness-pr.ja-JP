---
title: Skype for Business でコール パーク オービット範囲を作成または変更する
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Skype for Business Server の通話パーク オービット範囲テーブルを作成または変更エンタープライズ VoIP。
ms.openlocfilehash: eab1c3e6e53eaa878546b5fe4a9684147a00c583
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106323"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="9bd34-103">Skype for Business でコール パーク オービット範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="9bd34-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="9bd34-104">Skype for Business Server の通話パーク オービット範囲テーブルを作成または変更エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="9bd34-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="9bd34-105">コール パークは、駐車場の呼び出しにオービットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="9bd34-106">ユーザーが通話をパークおよび取得する前に、コール パーク オービット テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd34-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="9bd34-107">組織がパーキング 通話用に予約する内線番号 (オービット) の範囲を指定し、各範囲を処理するコール パーク プールを指定して、それらの範囲のルーティングを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd34-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="9bd34-108">オービット範囲を定義する場合、目標は十分なオービットを使用して、1 つのオービットがあまり速く再利用されるのではなく、ユーザーや他のサービスで使用できる拡張の数を制限するほど多くのオービットを使用しすぎることです。</span><span class="sxs-lookup"><span data-stu-id="9bd34-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="9bd34-109">通話パーク アプリケーションが展開されている Skype for Business Server プールごとに、複数のコール パーク オービット範囲を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9bd34-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="9bd34-110">各 Call Park オービット範囲には、グローバルに一意の名前と一意の拡張機能セットが必要です。</span><span class="sxs-lookup"><span data-stu-id="9bd34-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bd34-p102">一般的にオービット範囲には 100 未満のオービットが含まれます。 1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。 範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="9bd34-114">オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="9bd34-115">コール パーク オービット テーブルのオービット番号としてダイレクト インワード ダイヤル (DID) 番号を割り当てるのはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9bd34-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="9bd34-116">コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="9bd34-117">Skype for Business Server コントロール パネルを使用して、駐車通話の番号範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="9bd34-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="9bd34-p103">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="9bd34-120">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9bd34-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="9bd34-121">左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bd34-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="9bd34-122">[**コール パーク**] ページで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="9bd34-p104">新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="9bd34-125">オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9bd34-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="9bd34-p105">既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="9bd34-128">最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="9bd34-129">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9bd34-129">Be aware:</span></span>

   - <span data-ttu-id="9bd34-130">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9bd34-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="9bd34-131">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd34-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="9bd34-p107">オービット範囲は一意である必要があります。 この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="9bd34-134">オービット範囲が文字または #で始まる場合、範囲は 100 より大きい必要 \* があります。</span><span class="sxs-lookup"><span data-stu-id="9bd34-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="9bd34-135">有効な値: 正規表現文字列と一致する必要があります ([ \\ \*|#]?1-9]\d {0,7} )|([1-9]\d)。 {0,8}</span><span class="sxs-lookup"><span data-stu-id="9bd34-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="9bd34-136">つまり、値は、文字または # で始まる文字列か、1 ~ 9 の数値である必要があります (最初の文字は \* 0 にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="9bd34-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="9bd34-137">最初の文字が #の場合、次の文字は 1 ~ 9 の数値 \* である必要があります (ゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="9bd34-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="9bd34-138">後続の文字には、0 ~ 9 の任意の数字 \* ("#6000"、"92000"、"95551212"、"915551212"など) を指定できます。 \*</span><span class="sxs-lookup"><span data-stu-id="9bd34-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="9bd34-139">最初の文字が #または #の場合、最初の文字は 1 ~ 9 の数字 (ゼロにすることはできません)、その後に最大 8 文字の数字 (たとえば \* 、"915551212"、"41212"、"300" など) が続きます。</span><span class="sxs-lookup"><span data-stu-id="9bd34-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="9bd34-p109">プール当たりの合計が 50,000 オービットを超えないようにしてください。 各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。 たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="9bd34-p110">**[宛先サーバーの FQDN]** で、コール パーク アプリケーションをホストするアプリケーション サービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。 オービット範囲の開始番号と終了番号で指定された範囲の番号にパークされるすべての通話は、このサーバーまたはプールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9bd34-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="9bd34-145">**[確定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bd34-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="9bd34-146">Skype for Business Server 管理シェルを使用して、駐車通話の番号範囲を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="9bd34-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="9bd34-147">「代理セットアップのアクセス許可」の説明に従って、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9bd34-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="9bd34-148">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9bd34-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="9bd34-149">オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="9bd34-150">オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="9bd34-151">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="9bd34-152">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="9bd34-153">次の例は、既存のオービット範囲内の番号を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9bd34-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="9bd34-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bd34-154">See also</span></span>

[<span data-ttu-id="9bd34-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="9bd34-155">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="9bd34-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="9bd34-156">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="9bd34-157">コール パーク オービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="9bd34-157">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)