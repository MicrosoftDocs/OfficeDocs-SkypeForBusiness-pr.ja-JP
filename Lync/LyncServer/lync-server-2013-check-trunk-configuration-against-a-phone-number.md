---
title: 'Lync Server 2013: 電話番号に対してトランク構成を確認する'
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
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="bafa1-102">Lync Server 2013 で電話番号に対するトランク構成を確認する</span><span class="sxs-lookup"><span data-stu-id="bafa1-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bafa1-103">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="bafa1-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bafa1-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="bafa1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bafa1-105">毎月</span><span class="sxs-lookup"><span data-stu-id="bafa1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bafa1-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="bafa1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bafa1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bafa1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bafa1-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="bafa1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bafa1-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bafa1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bafa1-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、Get-cstrunkconfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bafa1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="bafa1-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bafa1-112">説明</span><span class="sxs-lookup"><span data-stu-id="bafa1-112">Description</span></span>

<span data-ttu-id="bafa1-113">SIP トランク Lync Server の内部エンタープライズ Voip ネットワークを次のいずれかに接続します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="bafa1-114">公衆交換電話網 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="bafa1-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="bafa1-115">IP パブリックブランチ exchange (PBX)。</span><span class="sxs-lookup"><span data-stu-id="bafa1-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="bafa1-116">セッションボーダーコントローラー (SBC)。</span><span class="sxs-lookup"><span data-stu-id="bafa1-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="bafa1-117">Get-cstrunkconfiguration コマンドレットでは、(ユーザーによってダイヤルされた) 電話番号を e.164 ネットワークに変換し、指定された SIP トランクを経由してルーティングできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bafa1-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="bafa1-118">Running the test</span></span>

<span data-ttu-id="bafa1-119">Get-cstrunkconfiguration コマンドレットを実行するには、最初に Get-cstrunkconfiguration コマンドレットを使用して SIP トランク構成設定のインスタンスを取得する必要があります。その後、そのインスタンスは Get-cstrunkconfiguration にパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="bafa1-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="bafa1-120">最初に Get-cstrunkconfiguration を実行せずにテストを実行すると、Get-cstrunkconfiguration は機能しません。</span><span class="sxs-lookup"><span data-stu-id="bafa1-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="bafa1-121">たとえば、次のコマンドは、データを返さずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="bafa1-122">SIP トランク構成設定のコレクションが複数ある場合は、次のようなコマンドを同時に使用して、各コレクションを同じ電話番号に対してテストできます。</span><span class="sxs-lookup"><span data-stu-id="bafa1-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="bafa1-123">詳細については、Get-cstrunkconfiguration コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bafa1-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bafa1-124">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="bafa1-124">Determining success or failure</span></span>

<span data-ttu-id="bafa1-125">Get-cstrunkconfiguration がダイヤル番号に電話をかけることができる場合は、(e.164 形式で) 翻訳された電話番号と、その電話番号の変換に使用されるルールの両方が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bafa1-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="bafa1-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="bafa1-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="bafa1-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="bafa1-127">\---------------- ------------</span></span>

<span data-ttu-id="bafa1-128">\+12065551219グローバル/Redmond</span><span class="sxs-lookup"><span data-stu-id="bafa1-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="bafa1-129">テストが失敗した場合、Get-cstrunkconfiguration は空のプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="bafa1-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="bafa1-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="bafa1-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="bafa1-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bafa1-132">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="bafa1-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="bafa1-133">Get-cstrunkconfiguration が一致を返さない場合、通常は、テスト対象のトランク構成設定に、ダイヤル番号を e.164 形式に変換できる発信通話番号変換ルールがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="bafa1-134">トランク構成設定のコレクションに割り当てられている変換ルールを取得するには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="bafa1-135">これにより、変換ルールごとに次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="bafa1-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="bafa1-136">説明: 国番号またはエリアコードのない電話番号。</span><span class="sxs-lookup"><span data-stu-id="bafa1-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="bafa1-137">パターン: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="bafa1-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="bafa1-138">名前: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="bafa1-138">Name : NoAreaCode</span></span>

<span data-ttu-id="bafa1-139">その時点で、Pattern プロパティ ([正規表現](https://go.microsoft.com/fwlink/?linkid=400464)文字列) の値をチェックして、いずれかの変換ルールがダイヤル番号を処理するように構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-139">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="bafa1-140">それ以外の場合は、既存のルールの1つを変更するか (New-csoutboundtranslationrule)、New-csoutboundtranslationrule コマンドレットを使用して新しいルールをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="bafa1-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bafa1-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="bafa1-141">See Also</span></span>


[<span data-ttu-id="bafa1-142">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="bafa1-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

