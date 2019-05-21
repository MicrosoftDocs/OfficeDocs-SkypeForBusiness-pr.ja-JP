---
title: 場所ポリシーの新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: 場所ポリシーを構成すると、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定することができます。
ms.openlocfilehash: e990001fae2d2754e83532f481f8e607d5971fb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291913"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="83b8a-103">場所のポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="83b8a-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="83b8a-104">場所ポリシーを構成すると、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="83b8a-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="83b8a-105">UI Reference</span></span>

<span data-ttu-id="83b8a-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="83b8a-107">**スコープ**作成または変更する場所ポリシーのスコープ (グローバル、サイト、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="83b8a-108">**名前**各場所のポリシーには名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="83b8a-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="83b8a-109">グローバルとサイトの場所のポリシーには既定で名前が付けられ、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="83b8a-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="83b8a-110">ユーザーの場所ポリシーでは、ユーザーまたはユーザーのグループを識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="83b8a-111">場所ポリシーを保存した後で、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="83b8a-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="83b8a-112">**拡張9-1-1 を有効にする (E9** -1)この場所のポリシーが割り当てられているユーザーに対して E9-1-1 を有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="83b8a-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="83b8a-113">**場所**場所情報の入力を求めるメッセージをユーザーに表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="83b8a-114">**必須**クライアントが新しい場所に登録されたときに位置情報を求められるようにするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="83b8a-115">ユーザーは、場所情報を入力せずにプロンプトを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="83b8a-116">**必須ではありません**ユーザーが場所情報の入力を求めるメッセージを表示しない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="83b8a-117">**免責事項**ユーザーが位置情報の入力を求めるメッセージを表示する場合は、このオプションを選択します。情報を入力せずにプロンプトを拒否した場合は、免責メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="83b8a-118">ユーザーは緊急通話を行うことができます。ただし、ユーザーが位置情報を入力するまでは、通話を発信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="83b8a-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="83b8a-119">**E9 の場所を使用する-1-** 1このチェックボックスをオンにすると、緊急通話にのみ地域情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="83b8a-120">**PSTN の利用状況**このプロファイルを使用するクライアントからの緊急通話のルーティングに使用されるボイスルートを決定するために使用される公衆交換電話網 (PSTN) 使用量を選択します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="83b8a-121">この使用に関連付けられているルートは、緊急通報専用の SIP トランクか、緊急通話を最も近い公安 (PSAP) にルーティングする緊急電話番号 (ELIN) のゲートウェイを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b8a-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="83b8a-122">オプションには、**内部**、**ローカル**、または**長距離**があります。</span><span class="sxs-lookup"><span data-stu-id="83b8a-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="83b8a-123">**E9-1-1 ダイヤル番号**緊急サービスに接続するためにダイヤルする番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="83b8a-124">**E9-1-1 ダイヤルマスク**ユーザーがダイヤルする番号を指定します。これは、緊急電話番号に変換されます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="83b8a-125">たとえば、このフィールドに212の値を入力すると、ユーザーは212をダイヤルして緊急サービスに連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="83b8a-126">これにより、別の緊急電話番号をダイヤルすることができます。たとえば、別の緊急電話番号を持つ国または地域のユーザーは、その国または地域の番号ではなく、その国または地域の電話番号にダイヤルします。現在の国または地域)。</span><span class="sxs-lookup"><span data-stu-id="83b8a-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="83b8a-127">値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="83b8a-128">たとえば、212;414 のように入力します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-128">For example, 212;414.</span></span> <span data-ttu-id="83b8a-129">文字列の最大の長さは、100文字です。</span><span class="sxs-lookup"><span data-stu-id="83b8a-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="83b8a-130">各文字は 0 ～ 9 の数字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b8a-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="83b8a-131">コールパークルーティングは緊急ダイヤルの文字列変換より優先されるため、ダイヤルマスクが通話パーク番号の範囲内の番号と同じではないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="83b8a-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="83b8a-132">通話パーク番号の範囲を確認するには、左側のナビゲーションバーで [**音声機能**] をクリックし、[**コールパーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83b8a-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="83b8a-133">**通知 URI**緊急通話が行われたときに通知される SIP Uri を1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="83b8a-134">たとえば、緊急通話が行われるたびに、セキュリティスタッフにインスタントメッセージを送信するように、会社のセキュリティ office SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="83b8a-135">呼び出し元の場所が利用可能な場合は、その場所が通知に含まれます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="83b8a-136">コンマ区切りリストとして複数の SIP Uri を指定できます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="83b8a-137">たとえば、"sip: security@litwareinc.com"、"sip: kmyer@litwareinc.com" のようになります。</span><span class="sxs-lookup"><span data-stu-id="83b8a-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="83b8a-138">文字列は、1 ~ 256 文字の長さで、先頭が "sip:" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b8a-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="83b8a-139">配布リストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="83b8a-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="83b8a-140">**会議の URI**サードパーティが緊急通話に conferenced できる SIP URI (この場合は電話番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="83b8a-141">たとえば、緊急通報が行われたときに通話を受信できるように、会社のセキュリティオフィスの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="83b8a-142">**会議モード**の設定では、サードパーティが参加できるか、または通話をリッスンするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="83b8a-143">文字列は、1 ~ 256 文字の長さで、先頭が「sip:」で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b8a-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="83b8a-144">**会議モード**[**会議 URI**] の値を指定した場合は、次の値のいずれかにこのフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="83b8a-145">**一方向**第三者が発信者と PSAP 演算子の間の呼び出しのみをリッスンできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="83b8a-146">**双方向**発信者と PSAP 演算子の間の通話に第三者が参加できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="83b8a-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="83b8a-147">エンタープライズ Voip サービスの機能と機能の詳細については、計画ドキュメントの「 [E9 の概要](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8a-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="83b8a-148">場所ポリシーの使用の詳細については、「操作」のドキュメントの「[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8a-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


