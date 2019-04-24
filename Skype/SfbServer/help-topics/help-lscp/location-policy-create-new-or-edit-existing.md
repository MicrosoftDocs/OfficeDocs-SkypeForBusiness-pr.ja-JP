---
title: 場所のポリシーを新規作成または既存の編集
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: 場所ポリシーを構成すると、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定することができます。
ms.openlocfilehash: 50769e3f6aec7d495ee5f9ea1c835c2e0849dc01
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200836"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="9ddf3-103">場所のポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="9ddf3-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="9ddf3-104">場所ポリシーを構成すると、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9ddf3-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="9ddf3-105">UI Reference</span></span>

<span data-ttu-id="9ddf3-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="9ddf3-107">**スコープ**作成または変更する場所ポリシーのスコープを識別します。 グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="9ddf3-108">**名**各場所のポリシーには、名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="9ddf3-109">グローバルおよびサイトの場所のポリシーが既定では、名前付きし、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="9ddf3-110">ユーザーの場所のポリシーのユーザーまたはユーザーのグループを識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ddf3-111">場所ポリシーを保存した後で、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="9ddf3-112">**拡張 9-1-1 (~ 9-1-1) を有効にします。** この場所のポリシーが割り当てられているユーザーに対して ~ 9-1-1 を有効にするには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="9ddf3-113">**場所**ユーザーが場所情報の確認を求めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="9ddf3-114">**必要な**ユーザーが、クライアントが新しい場所に登録するとする場所の情報を入力する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="9ddf3-115">ユーザーは、場所情報を入力することがなく、プロンプトを無視することが。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="9ddf3-116">**必須ではないです。** 場所の情報を入力しないようにユーザーがいる場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="9ddf3-117">**免責事項**ユーザーの場所については、メッセージを表示するのには情報を入力することがなく、プロンプトを選択しない場合は、免責事項メッセージが表示する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="9ddf3-118">ユーザーには、場所情報を入力するまで、緊急の呼び出しがないその他の呼び出しを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="9ddf3-119">**~ 9-1-1 のみの使用場所**場所については、緊急の呼び出しにのみ使用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="9ddf3-120">**PSTN の使用法**このプロファイルを使用するクライアントからの緊急通話のルーティングに使用するボイス ルートを決定する使用される公衆交換電話網 (PSTN) 使用法を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="9ddf3-121">この使用法に関連付けられている工順は、専用の緊急電話番号や緊急通報を最も近いパブリックの安全性への応答ポイント (PSAP) にルーティングする、緊急位置識別番号 (ELIN) ゲートウェイの SIP トランクをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="9ddf3-122">オプションは、**内部**、**ローカル**、または**遠隔地**です。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="9ddf3-123">**~ 9-1-1 は、番号をダイヤル**緊急サービスに到達するためにダイヤルする番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="9ddf3-124">**マスクをダイヤルする ~ 9-1-1**緊急ダイヤル番号に変換し、ユーザーがダイヤルする番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="9ddf3-125">たとえば、ユーザーが緊急サービスに到達するために 212 をダイヤルできるようにこのフィールドに 212 の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="9ddf3-126">これで代替の緊急番号にダイヤルして、緊急サービスに到達する呼び出しは、(他のユーザーが国または地域別の緊急電話番号にダイヤルする国または地域の番号の番号ではなく、しよう場合など、国または地域に取り付けられている)。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="9ddf3-127">値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="9ddf3-128">たとえば、212;414 のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-128">For example, 212;414.</span></span> <span data-ttu-id="9ddf3-129">文字列の最大長は、100 文字です。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="9ddf3-130">各文字は 0 ～ 9 の数字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9ddf3-131">ダイヤル マスクが確認されないコール パーク番号範囲の数値と同じ緊急ダイヤル文字列の変換より優先されますコール パーク ルーティングするためです。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="9ddf3-132">コール パークの番号範囲を表示するには、左側のナビゲーション ・ バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="9ddf3-133">**通知 URI**緊急の呼び出しが行われたときに通知する 1 つまたは複数の SIP Uri を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="9ddf3-134">たとえば、緊急の呼び出しが行われたときに、インスタント メッセージでのセキュリティ スタッフを通知するために会社の警備室の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="9ddf3-135">呼び出し元の場所が使用可能な場合は、通知の場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="9ddf3-136">コンマ区切りのリストとしては、複数の SIP Uri を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="9ddf3-137">"Sip:security@litwareinc.com"、"sip:kmyer@litwareinc.com"などです。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="9ddf3-138">文字列は 1 から 256 文字までにする必要があり、プレフィックスで始まる必要があります"sip:"です。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="9ddf3-139">配布リストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="9ddf3-140">**会議 URI**緊急電話番号に conferenced するサード パーティの SIP URI (この場合は電話番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="9ddf3-141">たとえば、緊急の呼び出しが行われると呼び出しを受信するように企業セキュリティ オフィスの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="9ddf3-142">**会議モード**の設定は、サード ・ パーティが参加したり、電話聴くだけかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="9ddf3-143">文字列は 1 から 256 文字までにする必要があり、プレフィックス sip で始まる必要があります: です。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="9ddf3-144">**会議モード\*\*\*\*会議の URI**の値を指定した場合は、次の値のいずれかにこのフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="9ddf3-145">**一方向**あるサード パーティ製受信のみが可能、発信者と PSAP オペレーターとの間の呼び出しを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="9ddf3-146">**双方向**サード ・ パーティが、発信者と PSAP オペレーターとの間の呼び出しで参加できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="9ddf3-147">エンタープライズ VoIP の緊急サービスの特徴と機能についての詳細は、計画ドキュメントの[概要の ~ 9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9ddf3-148">場所ポリシーの使用の詳細については、「操作」のドキュメントの「[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ddf3-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


