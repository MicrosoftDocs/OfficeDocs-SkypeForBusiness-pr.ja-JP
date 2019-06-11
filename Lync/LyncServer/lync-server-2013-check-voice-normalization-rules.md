---
title: 'Lync Server 2013: 音声正規化ルールを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="1c9ec-102">Lync Server 2013 で音声正規化ルールを確認する</span><span class="sxs-lookup"><span data-stu-id="1c9ec-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c9ec-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="1c9ec-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c9ec-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="1c9ec-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1c9ec-105">毎月</span><span class="sxs-lookup"><span data-stu-id="1c9ec-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c9ec-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="1c9ec-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1c9ec-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c9ec-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c9ec-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1c9ec-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1c9ec-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1c9ec-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoiceNormalizationRule コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="1c9ec-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1c9ec-112">説明</span><span class="sxs-lookup"><span data-stu-id="1c9ec-112">Description</span></span>

<span data-ttu-id="1c9ec-113">音声正規化規則は、ユーザーがダイヤルした電話番号 (2065551219 など) を、Lync Server (+ 12065551219) で使用される E.i 形式に変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="1c9ec-114">たとえば、国コードや市外局番を含めずに電話番号をダイヤルする習慣 (5551219 など) の場合、その番号を E.i 形式に変換するには、音声の正規化ルールを使用する必要があります (例: + 12065551219)。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="1c9ec-115">このようなルールがないと、ユーザーは555-1219 に通話を発信できません。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="1c9ec-116">CsVoiceNormalizationRule コマンドレットは、指定された音声正規化ルールが、指定された電話番号を正しく変換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="1c9ec-117">たとえば、このコマンドは、グローバル正規化ルール NoAreaCode が、ダイヤル文字列5551219を正規化して変換できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1c9ec-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="1c9ec-118">Running the test</span></span>

<span data-ttu-id="1c9ec-119">CsVoiceNormalizationRule コマンドレットを実行するには、最初に Get-CsVoiceNormalizationRule コマンドレットを使って、テスト対象のルールのインスタンスを取得し、そのインスタンスをテスト-CsVoiceNormalizationRule にパイプします。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="1c9ec-120">このような構文は、次のように動作しません。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="1c9ec-121">CsVoiceNormalizationRule-Ednumber "12065551219" – NormalizationRule "global/Prefix All"</span><span class="sxs-lookup"><span data-stu-id="1c9ec-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="1c9ec-122">代わりに、CsVoiceNormalizationRule と CsVoiceNormalizationRule コマンドレットの両方を組み合わせた次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="1c9ec-123">Get-CsVoiceNormalizationRule-Identity "global/Prefix All" |CsVoiceNormalizationRule-の番号 "12065551219" のテスト</span><span class="sxs-lookup"><span data-stu-id="1c9ec-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c9ec-124">.</span><span class="sxs-lookup"><span data-stu-id="1c9ec-124"></span></span> <span data-ttu-id="1c9ec-125">または、この方法を使用して、ルールのインスタンスを取得し、指定した電話番号に対してそのルールをテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="1c9ec-126">番号をダイヤルする場合と同じように、指定された番号パラメーターの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="1c9ec-127">たとえば、指定された音声正規化ルールが国コード (値12065551219の最初の 1) を自動的に追加する場合は、国コードをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="1c9ec-128">ルールが正しく構成されている場合は、電話番号を Lync Server で使用される E.i 形式に変換するときに、国コードが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="1c9ec-129">詳細については、「CsVoiceNormalizationRule コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1c9ec-130">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="1c9ec-130">Determining success or failure</span></span>

<span data-ttu-id="1c9ec-131">指定した音声正規化ルールで指定した番号が翻訳された場合は、翻訳後の番号が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="1c9ec-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="1c9ec-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="1c9ec-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="1c9ec-133">\+12065551219</span></span>

<span data-ttu-id="1c9ec-134">テストが失敗すると、空白の翻訳された数値が返されます。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="1c9ec-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="1c9ec-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1c9ec-136">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="1c9ec-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="1c9ec-137">CsVoiceNormalizationRule によって、指定された電話番号を、Lync Server で使用されている E.i 形式に変換できなかったことを示す、翻訳された数値が返される場合。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="1c9ec-138">これを確認するには、まず電話番号を正しく入力したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="1c9ec-139">たとえば、次のような数値の変換については、音声の正規化ルールで問題が発生していることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="1c9ec-140">番号が正しく入力されていることを前提として、次の手順は、指定された正規化ルールがその電話番号を処理するように設計されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="1c9ec-141">たとえば、1つの正規化ルールは12065551219の形式を処理するように設計されていますが、2つ目のルールは数値2065551219を処理するように設計されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="1c9ec-142">(これは同じ電話番号で、最初の国コード1を差し引いています)。音声正規化ルールに関する詳細情報を取得するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="1c9ec-143">すべての音声正規化ルールに関する詳細情報を取得するには、代わりに次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c9ec-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c9ec-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c9ec-144">See Also</span></span>


[<span data-ttu-id="1c9ec-145">テスト-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="1c9ec-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

