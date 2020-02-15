---
title: 'Lync Server 2013: 正規化ルールの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a09f5075ffe8ff267f31333d3dba0f4fffbc41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="caa9c-102">Lync Server 2013 での正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="caa9c-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caa9c-103">_**トピックの最終更新日:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="caa9c-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="caa9c-104">Lync Server 2013 の正規化ルールは、.NET Framework 正規表現を使用して、ダイヤルされた電話番号を e.164 形式に変換します。言い換えると、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Lync Server で内部的に使用される形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="caa9c-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="caa9c-105">各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa9c-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="caa9c-106">正規化ルールの詳細については、「計画」のドキュメントの「[ダイヤルプランと正規化ルール (Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa9c-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="caa9c-107">正規表現の記述方法の詳細については、「」の「.NET [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)Framework の正規表現」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa9c-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="caa9c-108">正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="caa9c-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="caa9c-109">[**正規化ルールの構築**] ツールを使用して、先頭の数字、長さ、削除する数字、追加する数字の値を指定し、Lync Server コントロールパネルで対応する一致パターンと変換ルールを生成するようにします。</span><span class="sxs-lookup"><span data-stu-id="caa9c-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="caa9c-110">正規表現を手動で記述し、一致パターンと変換ルールを定義する。</span><span class="sxs-lookup"><span data-stu-id="caa9c-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="caa9c-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="caa9c-111">In This Section</span></span>

  - [<span data-ttu-id="caa9c-112">「Lync Server 2013 で正規化ルールを構築する」を使用して正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="caa9c-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="caa9c-113">Lync Server 2013 で正規化ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="caa9c-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="caa9c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="caa9c-114">See Also</span></span>


[<span data-ttu-id="caa9c-115">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="caa9c-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="caa9c-116">Lync Server 2013 でダイヤルプランを変更する</span><span class="sxs-lookup"><span data-stu-id="caa9c-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

