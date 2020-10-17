---
title: 'Lync Server 2013: 電話番号に対してトランク構成を確認する'
description: 'Lync Server 2013: 電話番号に対してトランク構成を確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdfe1a2a9c5c87310ad561464960c5a01fea7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543543"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="9d693-103">Lync Server 2013 で電話番号に対するトランク構成を確認する</span><span class="sxs-lookup"><span data-stu-id="9d693-103">Check trunk configuration against a phone number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d693-104">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9d693-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d693-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="9d693-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9d693-106">毎月</span><span class="sxs-lookup"><span data-stu-id="9d693-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d693-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="9d693-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9d693-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d693-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d693-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9d693-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9d693-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d693-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9d693-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsTrunkConfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d693-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="9d693-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d693-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9d693-113">説明</span><span class="sxs-lookup"><span data-stu-id="9d693-113">Description</span></span>

<span data-ttu-id="9d693-114">SIP トランク Lync Server の内部エンタープライズ Voip ネットワークを次のいずれかに接続します。</span><span class="sxs-lookup"><span data-stu-id="9d693-114">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="9d693-115">公衆交換電話網 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="9d693-115">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="9d693-116">IP パブリックブランチ exchange (PBX)。</span><span class="sxs-lookup"><span data-stu-id="9d693-116">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="9d693-117">セッションボーダーコントローラー (SBC)。</span><span class="sxs-lookup"><span data-stu-id="9d693-117">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="9d693-118">Test-CsTrunkConfiguration コマンドレットでは、(ユーザーによってダイヤルされた) 電話番号を e.164 ネットワークに変換し、指定された SIP トランクを経由してルーティングできるかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="9d693-118">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9d693-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9d693-119">Running the test</span></span>

<span data-ttu-id="9d693-120">Test-CsTrunkConfiguration コマンドレットを実行するには、最初に Get-CsTrunkConfiguration コマンドレットを使用して SIP トランク構成設定のインスタンスを取得する必要があります。その後、そのインスタンスは Get-cstrunkconfiguration にパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d693-120">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9d693-121">最初に Get-CsTrunkConfiguration を実行せずに Test-CsTrunkConfiguration を実行しても動作しません。</span><span class="sxs-lookup"><span data-stu-id="9d693-121">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="9d693-122">たとえば、次のコマンドは、データを返さずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9d693-122">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="9d693-123">SIP トランク構成設定のコレクションが複数ある場合は、次のようなコマンドを同時に使用して、各コレクションを同じ電話番号に対してテストできます。</span><span class="sxs-lookup"><span data-stu-id="9d693-123">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9d693-124">詳細については、Test-CsTrunkConfiguration コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d693-124">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9d693-125">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="9d693-125">Determining success or failure</span></span>

<span data-ttu-id="9d693-126">Test-CsTrunkConfiguration がダイヤル番号に電話をかけることができる場合は、(e.164 形式で) 翻訳された電話番号と、その電話番号の変換に使用されるルールの両方が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d693-126">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="9d693-127">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9d693-127">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9d693-128">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9d693-128">\---------------- ------------</span></span>

<span data-ttu-id="9d693-129">\+12065551219グローバル/Redmond</span><span class="sxs-lookup"><span data-stu-id="9d693-129">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="9d693-130">テストが失敗すると、Test-CsTrunkConfiguration は空のプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="9d693-130">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="9d693-131">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9d693-131">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9d693-132">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9d693-132">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9d693-133">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="9d693-133">Reasons why the test might have failed</span></span>

<span data-ttu-id="9d693-134">Test-CsTrunkConfiguration が一致を返さない場合、通常は、テスト対象のトランク構成設定に、ダイヤル番号を e.164 形式に変換できる発信通話番号変換ルールがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d693-134">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="9d693-135">トランク構成設定のコレクションに割り当てられている変換ルールを取得するには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d693-135">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="9d693-136">これにより、変換ルールごとに次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="9d693-136">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="9d693-137">説明: 国番号またはエリアコードのない電話番号。</span><span class="sxs-lookup"><span data-stu-id="9d693-137">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="9d693-138">パターン: ^ \\ + ( \\ d \* ) $</span><span class="sxs-lookup"><span data-stu-id="9d693-138">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="9d693-139">名前: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="9d693-139">Name : NoAreaCode</span></span>

<span data-ttu-id="9d693-140">その時点で、Pattern プロパティ ( [正規表現](https://go.microsoft.com/fwlink/?linkid=400464) 文字列) の値をチェックして、いずれかの変換ルールがダイヤル番号を処理するように構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9d693-140">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="9d693-141">それ以外の場合は、既存のルールの1つを変更するか (New-csoutboundtranslationrule)、または New-CsOutboundTranslationRule コマンドレットを使用して新しいルールをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="9d693-141">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d693-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d693-142">See Also</span></span>


[<span data-ttu-id="9d693-143">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="9d693-143">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

