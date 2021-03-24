---
title: Call Park Create New or Edit Existing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 呼び出しパーク番号の範囲は、パークされた通話が保持される一時的な番号を定義します。その番号は、他のユーザーが通話を取得するか、または時間が切れるまで保持されます。
ms.openlocfilehash: 1a85bacf1ebb13afd7302f8e1cf50c112c3139e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095681"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="2ae52-103">コール パーク: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="2ae52-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="2ae52-104">呼び出しパーク番号の範囲は、パークされた通話が保持される一時的な番号を定義します。その番号は、他のユーザーが通話を取得するか、または時間が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="2ae52-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2ae52-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="2ae52-105">UI Reference</span></span>

<span data-ttu-id="2ae52-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="2ae52-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2ae52-107">**名前** 番号範囲を識別するわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ae52-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="2ae52-108">番号範囲を保存した後、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ae52-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="2ae52-109">**数値範囲** 最初のフィールドに、番号範囲の先頭番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ae52-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="2ae52-110">2 番目のフィールドに、数値範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ae52-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="2ae52-111">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2ae52-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="2ae52-112">範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae52-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="2ae52-p103">番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2ae52-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="2ae52-115">数値範囲が文字または #で始まる場合、範囲は 100 より大きい必要 \* があります。</span><span class="sxs-lookup"><span data-stu-id="2ae52-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="2ae52-116">有効な値: 正規表現文字列と一致する必要があります ([ \\ \*|#]?1-9]\d {0,7} )|([1-9]\d)。 {0,8}</span><span class="sxs-lookup"><span data-stu-id="2ae52-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="2ae52-117">つまり、値は、文字または # で始まる文字列か、1 ~ 9 の数値である必要があります (最初の文字は \* 0 にすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="2ae52-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="2ae52-118">最初の文字が #の場合、次の文字は 1 ~ 9 の数値 \* である必要があります (ゼロにすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="2ae52-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="2ae52-119">後続の文字には、0 ~ 9 の任意の数字 \* ("#6000"、"92000"、"95551212"、"915551212"など) を指定できます。 \*</span><span class="sxs-lookup"><span data-stu-id="2ae52-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="2ae52-120">最初の文字がまたは #の場合、最初の文字は 1 ~ 9 の数字 (ゼロにすることはできません)、その後に最大 8 文字、それぞれ 0 ~ 9 の数字 \* (例: 915551212;41212;300) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae52-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="2ae52-p105">プール当たりの番号の合計数が 50,000 件を超えないようにしてください。各番号範囲は、通常、100 以下の番号を含みますが、10,000 件を超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2ae52-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="2ae52-124">**宛先サーバーの FQDN** コール パーク アプリケーションをホストする Application サービスの完全修飾ドメイン名 (FQDN) またはサービス ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ae52-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="2ae52-125">番号範囲内の開始番号と終了番号で指定された範囲内の番号に対してパークされているすべての呼び出しは、このサーバーまたはプールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="2ae52-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="2ae52-126">通話パークの機能の詳細については [、「Plan for Call Park in Skype for Business 2015」を参照してください](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae52-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="2ae52-127">コール パーク番号範囲の操作の詳細については [、「Configure Phone Number Extensions for Parking Call」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)。</span><span class="sxs-lookup"><span data-stu-id="2ae52-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>