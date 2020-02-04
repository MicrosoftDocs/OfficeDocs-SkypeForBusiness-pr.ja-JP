---
title: コールパーク新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: '[コールパーク番号の範囲を指定すると、他のユーザーが受信した場合またはタイムアウトした場合に、保留中の通話が保留になる一時的な番号が定義されます'
ms.openlocfilehash: 5f32cccf70593ffe480cbcba028974cc1dc91046
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703932"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="8c293-103">コール パーク: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="8c293-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="8c293-104">[コールパーク番号の範囲を指定すると、他のユーザーが受信した場合またはタイムアウトした場合に、保留中の通話が保留になる一時的な番号が定義されます</span><span class="sxs-lookup"><span data-stu-id="8c293-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8c293-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="8c293-105">UI Reference</span></span>

<span data-ttu-id="8c293-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="8c293-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="8c293-107">**名前**数値の範囲を示すわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c293-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="8c293-108">数値の範囲を保存した後は、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c293-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="8c293-109">**数値の範囲**最初のフィールドに番号範囲の開始番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c293-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="8c293-110">2番目のフィールドに、番号範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c293-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="8c293-111">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8c293-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="8c293-112">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c293-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="8c293-p103">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8c293-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="8c293-115">数値の範囲が文字\*または # で始まる場合、範囲は100よりも大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8c293-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="8c293-116">有効な値: 正規表現文字列と一致する必要\\があります ([\* | #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8})</span><span class="sxs-lookup"><span data-stu-id="8c293-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="8c293-117">つまり、文字\*または # のいずれかから始まる文字列、または 1 ~ 9 の数値 (最初の文字はゼロにすることはできません) であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8c293-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="8c293-118">最初の文字が\*または # の場合、次の文字は 1 ~ 9 の数字にする必要があります (0 にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="8c293-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="8c293-119">後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば、"#6000"\*、"92000"\*、"95551212"、"915551212")。</span><span class="sxs-lookup"><span data-stu-id="8c293-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="8c293-120">最初の文字が "not \* " または "#" である場合、最初の文字は 1 ~ 9 の数字 (0 にすることはできません)、最大8文字 (たとえば、915551212; 41212; 300) となります。</span><span class="sxs-lookup"><span data-stu-id="8c293-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="8c293-p105">プール当たりの番号の合計数が 50,000 件を超えないようにしてください。各番号範囲は、通常、100 以下の番号を含みますが、10,000 件を超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8c293-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="8c293-124">**転送先サーバーの FQDN**コールパークアプリケーションをホストするアプリケーションサービスの完全修飾ドメイン名 (FQDN) またはサービス ID を選びます。</span><span class="sxs-lookup"><span data-stu-id="8c293-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="8c293-125">番号範囲の開始番号と終了番号で指定された範囲内の番号に保留されているすべての通話が、このサーバーまたはプールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8c293-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="8c293-126">コールパーク機能と機能の詳細については、「 [Skype For business でのコールパークの計画](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c293-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="8c293-127">通話パーク番号範囲の使用について詳しくは、「[パーキング通話用に電話番号の内線番号を設定する](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c293-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


