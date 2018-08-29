---
title: 会議ポリシーを新規作成または既存の編集
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: 会議ポリシーにより、会議 (ミーティングとも呼ばれます) でユーザーが使用できる機能が定義されます。
ms.openlocfilehash: 6dbdb4a300e899e5172785cc08b081852a2c9742
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262352"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="50125-103">会議ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="50125-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="50125-104">会議ポリシーにより、会議 (ミーティングとも呼ばれます) でユーザーが使用できる機能が定義されます。</span><span class="sxs-lookup"><span data-stu-id="50125-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="50125-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="50125-105">UI Reference</span></span>

<span data-ttu-id="50125-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="50125-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="50125-107">**スコープ**作成または変更する会議ポリシーのスコープを識別します。 グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="50125-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="50125-108">**名**各会議ポリシーでは、名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="50125-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="50125-109">グローバルおよびサイトの会議ポリシーが既定では、名前付きし、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="50125-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="50125-110">ユーザー会議ポリシーは、ユーザーまたはユーザーのグループを識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="50125-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50125-111">この名前は、会議ポリシーの保存後には変更できません。</span><span class="sxs-lookup"><span data-stu-id="50125-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="50125-112">**説明**このフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="50125-112">**Description** This field is optional.</span></span> <span data-ttu-id="50125-113">会議ポリシーに関する追加情報を提供するのにには、それを使用します。</span><span class="sxs-lookup"><span data-stu-id="50125-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="50125-114">**開催者ポリシー**このセクションの設定は、会議を整理するユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="50125-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="50125-115">設定を選択すると、ユーザーが指定した特性を持つ会議を整理できます。</span><span class="sxs-lookup"><span data-stu-id="50125-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="50125-116">設定が選択されていない場合、ユーザーは、この特性との会議をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="50125-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="50125-117">これらの設定はどのようなユーザーが持っているへのアクセスを決定していないその他の会議に参加者として。</span><span class="sxs-lookup"><span data-stu-id="50125-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="50125-118">セクションを開いたり閉じたりするには、ラベルの横にある上矢印および下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50125-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="50125-119">**最大会議サイズ**会議で許可されているユーザーの最大数です。</span><span class="sxs-lookup"><span data-stu-id="50125-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="50125-120">既定で、会議の最大サイズは 250 です。</span><span class="sxs-lookup"><span data-stu-id="50125-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="50125-121">**匿名ユーザーを招待する参加者を許可します。** この会議への匿名ユーザーを招待するユーザーを許可する] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="50125-122">匿名ユーザーは、したがって、組織の Active Directory ドメイン サービスと、ユーザーの資格情報がない、認証されていないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="50125-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="50125-123">**記録**参加者が会議を記録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="50125-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="50125-124">オプションは、**なし**] または [**レコーディングを有効**にされます。</span><span class="sxs-lookup"><span data-stu-id="50125-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="50125-125">**フェデレーションを許可して匿名の参加者を記録するには**レコードの会議におよび認証されていない外部の参加者を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="50125-126">**オーディオ/ビデオ**参加者がオーディオとビデオを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="50125-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="50125-127">**なし**オーディオとビデオの使用を禁止するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="50125-128">**IP を有効にするオーディオ**オーディオがないビデオの使用を許可する] このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="50125-129">**有効にする IP オーディオ/ビデオ**オーディオとビデオの両方を許可するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="50125-130">**有効にする PSTN ダイヤルイン会議****オーディオとビデオ**のオーディオを有効にする場合は、ユーザーが公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできるようにするには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="50125-131">**ダイヤルアウトするのには匿名の参加者を許可します。** 会議にダイヤルインするユーザーを許可して、1 軒ずつ訪ねてアウト ダイヤルを使用して会議に参加するのには、認証されていない (匿名) ユーザーを許可する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="50125-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="50125-132">会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="50125-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="50125-133">**ダイヤルアウト用にエンタープライズ VoIP を有効になっていない参加者に許可します。****オーディオとビデオ**のオーディオを有効にする場合は、ダイアル アウトに電話を使用して会議に参加するのには、エンタープライズ VoIP で有効でないユーザーを許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="50125-134">ダイヤルアウト用のサーバーは、ユーザーを電話し、ユーザーが会議に参加するのには電話に応答する、会議を集めます。</span><span class="sxs-lookup"><span data-stu-id="50125-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="50125-135">**複数のビデオ ストリームを許可します。****オーディオとビデオ**のビデオを有効にする場合は、ギャラリーの表示のビデオ会議を整理するためにユーザーを許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="50125-136">このチェック ボックスをオンにすると、この設定は複数のビデオ ストリームを送信する会議を整理するためにユーザーをできます。</span><span class="sxs-lookup"><span data-stu-id="50125-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="50125-137">このチェック ボックスをオフにすると場合、ユーザーはのみ 1 つのビデオ ストリームを送信する会議を整理できます。</span><span class="sxs-lookup"><span data-stu-id="50125-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50125-p110">このオプションによって、会議でサポートされるビデオ ストリームの種類が決まります。参加者が複数のビデオ ストリームを受信できるかどうかは、このオプションで決まりません。[**複数のビデオ ストリームでの参加を参加者に許可する**] オプションによって、参加者が複数のビデオ ストリームを受信できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="50125-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="50125-141">**共同作業データ**会議が共同作業データを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="50125-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="50125-142">オプションは、**なし**または**データの共同作業を有効にする**には。</span><span class="sxs-lookup"><span data-stu-id="50125-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="50125-143">次の設定はデータのグループ作業に適用されます。</span><span class="sxs-lookup"><span data-stu-id="50125-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="50125-144">**フェデレーションを許可] と [コンテンツをダウンロードするのには匿名の参加者**共同作業データを許可する場合は、会議からのスライドや配布資料などのコンテンツをダウンロードするのには外部および未認証のユーザーを許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="50125-145">**ファイルを転送する参加者を許可します。** 共同作業データを許可する場合は、会議中にすべての参加者にファイル転送を許可する] このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="50125-146">**注釈を有効にします。** 共同作業データを許可する場合は、画面に表示されるようにするのには参加者を許可するには、このチェック ボックスを選択して、会議中に共有されているコンテンツの注釈。</span><span class="sxs-lookup"><span data-stu-id="50125-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="50125-147">**有効にする PowerPoint の注釈**コメントを許可する場合は、参加者が会議中に共有の PowerPoint スライドにコメントを追加を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="50125-148">**ポーリングを有効にします。** 共同作業データを許可する場合は、会議中に投票を保持するために参加者を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="50125-149">**アプリケーションの共有**会議では、アプリケーションを共有できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="50125-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="50125-150">オプションは、**アプリケーションの共有を無効にする**か、**アプリケーションの共有を有効にする**には。</span><span class="sxs-lookup"><span data-stu-id="50125-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="50125-151">次の設定はアプリケーション共有に適用されます。</span><span class="sxs-lookup"><span data-stu-id="50125-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="50125-152">**制御する参加者を許可します。** アプリケーションの共有を許可する場合は、アプリケーションや、会議中に共有されているデスクトップを制御する参加者を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="50125-153">**フェデレーションを許可して匿名の参加者に制御するのには**アプリケーションの共有を許可する場合は、アプリケーションや、会議中に共有されているデスクトップの制御および認証されていない外部の参加者を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="50125-154">**参加者のポリシー**このセクションの設定は、会議または 2 パーティ セッションに参加者として、ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="50125-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="50125-155">次の設定は、ユーザーごとの設定は、会議、または 2 パーティ セッションに 1 つのユーザー、同じ会議 2 パーティ セッションに他のユーザーよりも機能が異なるがあります。</span><span class="sxs-lookup"><span data-stu-id="50125-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="50125-156">セクションを開いたり閉じたりするには、ラベルの横にある上矢印および下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50125-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="50125-p114">[**アプリケーションとデスクトップの共有を有効にする**] を選択すると、会議または 2 者間セッションへの参加中にユーザーにアプリケーションまたはデスクトップの共有が許可されます。[**アプリケーションとデスクトップの共有を無効にする**] を選択すると、会議または 2 者間セッションへの参加中にユーザーにアプリケーションまたはデスクトップの共有が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="50125-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="50125-159">**ピア ツー ピア ファイル転送を有効にします。** 2 パーティ セッションや会議中にユーザー間のファイル転送 (つまり、すべての参加者と関係のないファイル転送) を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="50125-160">**ピア ツー ピアの記録を有効にします。** 2 パーティ セッションを記録するようにユーザーを許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="50125-161">**参加者は、複数のビデオ ストリームとの結合を有効にします。** ビデオのギャラリーの表示が表示されることができる会議に参加者を許可するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50125-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="50125-162">このオプションが選択されていない場合は、参加者はのみにより、会議の内容に関係なく 1 つのビデオ ストリームを受信できます。</span><span class="sxs-lookup"><span data-stu-id="50125-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50125-163">[**複数のビデオ ストリームを許可する**] は、会議で複数のビデオ ストリームを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="50125-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="50125-164">会議の機能と機能の詳細については、計画のドキュメントで[会議の概要](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50125-164">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="50125-165">会議ポリシーの使用についての詳細は、[会議ポリシー](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)操作マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50125-165">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


