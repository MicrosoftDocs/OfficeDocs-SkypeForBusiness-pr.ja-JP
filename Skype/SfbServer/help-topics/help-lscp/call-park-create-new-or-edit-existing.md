---
title: コール パークを新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: コール パーク番号範囲では、一時停止の呼び出しが誰かを取得するか、タイムアウトするまで保持される数値を定義します。
ms.openlocfilehash: 4788cf3bf51785005d88dbde6977f7f86e2efbb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916043"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="7a5fe-103">コール パーク: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="7a5fe-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="7a5fe-104">コール パーク番号範囲では、一時停止の呼び出しが誰かを取得するか、タイムアウトするまで保持される数値を定義します。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7a5fe-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="7a5fe-105">UI Reference</span></span>

<span data-ttu-id="7a5fe-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7a5fe-107">**名**番号の範囲を識別するわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="7a5fe-108">番号の範囲を保存すると、この名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="7a5fe-109">**番号の範囲**最初のフィールドで、番号の範囲の開始番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="7a5fe-110">2 番目のフィールドには、番号の範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="7a5fe-111">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="7a5fe-112">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="7a5fe-p103">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="7a5fe-115">番号の範囲が、文字で始まる場合\*#、範囲は 100 より大きい値である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="7a5fe-116">有効な値: 正規表現の文字列に一致する必要があります ([\\* | #] ? [1-9] \d{0,7})。(1 ~ 9 の \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="7a5fe-117">つまり、値は、いずれかの文字で始まる文字列である必要があります\*#、または数字 1 ~ 9 の (最初の文字はゼロであることはできません)。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="7a5fe-118">最初の文字の場合\*#、次の文字は数字 1 ~ 9 の (0 にすることはできません) である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="7a5fe-119">以降の文字は、任意の数の 0 から 9 までの 7 つの追加文字を使用できます (たとえば、「#6000」、「\*92000"、"\*95551212"、および"915551212").</span><span class="sxs-lookup"><span data-stu-id="7a5fe-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="7a5fe-120">最初の文字がない場合\*#、最初の文字は、最大 8 個までの文字の後に数字 1 ~ 9 (0 にすることはできません) である必要がありますか各数字 0 ~ 9 (例: 915551212、41212; 300)。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="7a5fe-p105">プール当たりの番号の合計数が 50,000 件を超えないようにしてください。各番号範囲は、通常、100 以下の番号を含みますが、10,000 件を超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="7a5fe-124">**宛先サーバーの FQDN**サービス ・ コール パーク アプリケーションをホストするアプリケーション サービスの ID または完全修飾ドメイン名 (FQDN) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="7a5fe-125">すべての呼び出しは、開始番号で指定された範囲内の数値に駐機しているし、番号の範囲の終了番号は、このサーバーまたはプールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="7a5fe-126">コール パークの特徴と機能についての詳細は、[ビジネス 2015年の Skype のコール パークの計画](../../plan-your-deployment/enterprise-voice-solution/call-park.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="7a5fe-127">コール パーク番号範囲の操作についての詳細は、[呼び出しの駐車場の電話番号の拡張機能を構成する](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a5fe-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


