---
title: 'Lync Server 2013: 電話番号に対してトランクの構成を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="811ca-102">Lync Server 2013 での電話番号に対するトランクの構成を確認する</span><span class="sxs-lookup"><span data-stu-id="811ca-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="811ca-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="811ca-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="811ca-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="811ca-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="811ca-105">毎月</span><span class="sxs-lookup"><span data-stu-id="811ca-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="811ca-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="811ca-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="811ca-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="811ca-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="811ca-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="811ca-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="811ca-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="811ca-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="811ca-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、Set-cstrunkconfiguration コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="811ca-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="811ca-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="811ca-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="811ca-112">説明</span><span class="sxs-lookup"><span data-stu-id="811ca-112">Description</span></span>

<span data-ttu-id="811ca-113">SIP trunks Lync Server の内部エンタープライズボイスネットワークを次のいずれかに接続します。</span><span class="sxs-lookup"><span data-stu-id="811ca-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="811ca-114">公衆交換電話網 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="811ca-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="811ca-115">IP 公衆支店交換 (PBX)。</span><span class="sxs-lookup"><span data-stu-id="811ca-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="811ca-116">セッション境界コントローラー (SBC)。</span><span class="sxs-lookup"><span data-stu-id="811ca-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="811ca-117">Set-cstrunkconfiguration コマンドレットは、電話番号 (ユーザーによってダイヤルされた番号) を E.i ネットワークに変換し、指定された SIP トランクを介してルーティングできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="811ca-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="811ca-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="811ca-118">Running the test</span></span>

<span data-ttu-id="811ca-119">Set-cstrunkconfiguration コマンドレットを実行するには、最初に Get-Set-cstrunkconfiguration コマンドレットを使用して SIP トランク構成設定のインスタンスを取得する必要があります。このインスタンスは、Set-cstrunkconfiguration にパイプラインとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="811ca-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="811ca-120">Set-cstrunkconfiguration を実行していない場合、Set-cstrunkconfiguration は動作しません。</span><span class="sxs-lookup"><span data-stu-id="811ca-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="811ca-121">たとえば、次のコマンドは、データを返さずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="811ca-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="811ca-122">SIP トランク構成設定のコレクションが複数ある場合は、次のようなコマンドを同時に使用して、各コレクションを同じ電話番号に対してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="811ca-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="811ca-123">詳細については、「Set-cstrunkconfiguration コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811ca-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="811ca-124">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="811ca-124">Determining success or failure</span></span>

<span data-ttu-id="811ca-125">Set-cstrunkconfiguration でダイヤルされた電話番号に通話を発信できる場合、翻訳された電話番号 (E.i 形式) と、その電話番号の翻訳に使用するルールは両方とも画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="811ca-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="811ca-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="811ca-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="811ca-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="811ca-127"></span></span>

<span data-ttu-id="811ca-128">\+12065551219グローバル/レドモンド</span><span class="sxs-lookup"><span data-stu-id="811ca-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="811ca-129">テストに失敗した場合、Set-cstrunkconfiguration は空のプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="811ca-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="811ca-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="811ca-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="811ca-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="811ca-131"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="811ca-132">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="811ca-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="811ca-133">Set-cstrunkconfiguration によって一致が返されない場合、通常は、テスト対象のトランク構成設定に、ダイヤルされた番号を E.i 形式に変換できる発信呼び出し番号の翻訳ルールがありません。</span><span class="sxs-lookup"><span data-stu-id="811ca-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="811ca-134">トランク構成設定のコレクションに割り当てられている翻訳ルールを取得するには、次のような構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="811ca-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="811ca-135">これは、翻訳ルールごとに次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="811ca-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="811ca-136">説明: 国コードまたは市外局番のない電話番号。</span><span class="sxs-lookup"><span data-stu-id="811ca-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="811ca-137">パターン: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="811ca-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="811ca-138">名前: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="811ca-138">Name : NoAreaCode</span></span>

<span data-ttu-id="811ca-139">この時点で、Pattern プロパティの値 ([正規表現](http://go.microsoft.com/fwlink/?linkid=400464)の文字列) をチェックして、いずれかの翻訳ルールがダイヤルされた番号を処理するように構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="811ca-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="811ca-140">存在しない場合は、既存の規則 (CsOutboundTranslationRule) のいずれかを変更するか、CsOutboundTranslationRule コマンドレットを使用して新しいルールをコレクションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="811ca-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="811ca-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="811ca-141">See Also</span></span>


[<span data-ttu-id="811ca-142">テスト-Set-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="811ca-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

