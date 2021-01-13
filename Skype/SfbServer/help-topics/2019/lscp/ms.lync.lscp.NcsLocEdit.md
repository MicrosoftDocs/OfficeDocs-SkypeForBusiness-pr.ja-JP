---
title: 場所ポリシーの作成 (新規) または [既存の編集]
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: 場所ポリシーを構成して、拡張 9-1-1 (E9-1-1) が有効になっているかどうか、その使用方法、およびユーザーと連絡先の場所情報の使用方法を決定できます。
ms.openlocfilehash: c1b1c21af9b0bee72e7b870f6252fdb118ee88d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836527"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="8cba7-103">場所ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="8cba7-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="8cba7-104">場所ポリシーを構成して、拡張 9-1-1 (E9-1-1) が有効になっているかどうか、その使用方法、およびユーザーや連絡先に対して場所情報がどのように使用されるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8cba7-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="8cba7-105">UI Reference</span></span>

<span data-ttu-id="8cba7-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="8cba7-107">**スコープ** 作成または変更する場所ポリシーの範囲 (グローバル、サイト、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="8cba7-108">**名前** 各場所ポリシーには名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="8cba7-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="8cba7-109">グローバルおよびサイトの場所のポリシーには既定で名前が付けられたので、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8cba7-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="8cba7-110">ユーザーの場所ポリシーの場合は、ユーザーまたはユーザーのグループを識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cba7-111">場所ポリシーを保存した後で、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8cba7-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="8cba7-112">**Enhanced 9-1-1 を有効にする (E9-1-1)** この場所ポリシーが割り当てられているユーザーに対して E9-1-1 を有効にするには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8cba7-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="8cba7-113">**場所** ユーザーに場所情報の入力を求めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="8cba7-114">**必須** クライアントが新しい場所に登録するときに場所情報の入力を求めるメッセージをユーザーに表示する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="8cba7-115">ユーザーは、場所情報を入力せずにプロンプトを閉じできます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="8cba7-116">**必須ではない** ユーザーに位置情報の入力を求めない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="8cba7-117">**免責事項** ユーザーに場所情報の入力を求めるメッセージが表示されるが、情報を入力せずにプロンプトを辞退すると免責事項メッセージが表示される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="8cba7-118">ユーザーは緊急電話を完了できますが、場所情報を入力するまで他の通話は完了しません。</span><span class="sxs-lookup"><span data-stu-id="8cba7-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="8cba7-119">**E9-1-1 でのみ場所を使用する** 場所情報を緊急電話にのみ使用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8cba7-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="8cba7-120">**PSTN 使用法** このプロファイルを使用するクライアントからの緊急通話のルーティングに使用するボイス ルートを決定するために使用する公衆交換電話網 (PSTN) 使用法を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="8cba7-121">この使用法に関連付けられているルートは、緊急電話専用の SIP トランク、または緊急通話を最も近い緊急応答ポイント (PSAP) にルーティングする緊急位置識別番号 (ELIN) ゲートウェイを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cba7-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="8cba7-122">オプションは **、内部、\*\*\*\*ローカル、** または **長距離です**。</span><span class="sxs-lookup"><span data-stu-id="8cba7-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="8cba7-123">**E9-1-1 ダイヤル番号** 緊急サービスに到達するためにダイヤルされる番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="8cba7-124">**E9-1-1 ダイヤル マスク** ユーザーがダイヤルする番号を指定すると、緊急ダイヤル番号に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="8cba7-125">たとえば、ユーザーが 212 をダイヤルして緊急サービスにアクセスできるよう、このフィールドに値 212 を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="8cba7-126">これにより、別の緊急電話番号をダイヤルし、緊急サービスに通話を発信できます (たとえば、緊急電話番号が異なる国または地域のユーザーが、現在の国または地域の番号ではなく、その国または地域の番号にダイヤルしようとした場合)。</span><span class="sxs-lookup"><span data-stu-id="8cba7-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="8cba7-127">値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="8cba7-128">たとえば、212;414 などです。</span><span class="sxs-lookup"><span data-stu-id="8cba7-128">For example, 212;414.</span></span> <span data-ttu-id="8cba7-129">文字列の最大長は 100 文字です。</span><span class="sxs-lookup"><span data-stu-id="8cba7-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="8cba7-130">各文字は 0 ～ 9 の数字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cba7-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8cba7-131">コール パーク ルーティングは緊急ダイヤル文字列変換よりも優先されるので、ダイヤル マスクがコール パーク番号範囲内の番号と同じでいなことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cba7-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="8cba7-132">コール パーク番号の範囲を表示するには、左側のナビゲーション バーの [ **音声** 機能] をクリックし、[コール パーク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8cba7-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="8cba7-133">**通知 URI** 緊急電話が行われたときに通知する 1 つ以上の SIP URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="8cba7-134">たとえば、会社のセキュリティ オフィスの SIP URI を入力して、緊急電話が行われたときにセキュリティ スタッフにインスタント メッセージを通知します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="8cba7-135">発信者の場所が使用可能な場合は、その場所が通知に含まれます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="8cba7-136">複数の SIP URI をコンマ区切りリストとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="8cba7-137">たとえば、"sip:security@litwareinc.com","sip:kmyer@litwareinc.com"。</span><span class="sxs-lookup"><span data-stu-id="8cba7-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="8cba7-138">文字列の長さは 1 ~ 256 文字で、プレフィックス "sip:" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cba7-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="8cba7-139">配布リストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8cba7-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="8cba7-140">**電話会議 URI** サードパーティが緊急電話に参加する SIP URI (この場合は電話番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="8cba7-141">たとえば、会社のセキュリティ オフィスの電話番号を入力して、緊急電話がかっているときに電話を受け取る場合などです。</span><span class="sxs-lookup"><span data-stu-id="8cba7-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="8cba7-142">会議モードの **設定では、** サード パーティが通話に参加できるかどうか、または通話を聞くだけの方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="8cba7-143">この文字列は 1 ～ 256 文字の長さで、プレフィックス sip: で始まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cba7-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="8cba7-144">**会議モード** 会議 URI に値を **指定した場合** は、このフィールドを次のいずれかの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="8cba7-145">**一方通行** 第三者が発信者と PSAP オペレーターとの間の通話のみを聞き取り可能に指定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="8cba7-146">**2 つの方法** 第三者が発信者と PSAP オペレーター間の通話に参加できるよう指定します。</span><span class="sxs-lookup"><span data-stu-id="8cba7-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="8cba7-147">緊急サービスのエンタープライズ VoIPの詳細については、「計画」のドキュメントの [「E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cba7-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="8cba7-148">場所ポリシーの操作の詳細については、「操作」のドキュメントの「[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cba7-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


