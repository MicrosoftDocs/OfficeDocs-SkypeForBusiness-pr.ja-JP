---
title: 会議ポリシー [新規の作成] または [既存の編集]
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
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: 会議ポリシーは、会議中にユーザーが利用できる機能 (会議とも呼ばれる) を定義します。
ms.openlocfilehash: 073019a46e2934f78ec0f20b8a7cb8e04c01bab9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121020"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="810a5-103">会議ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="810a5-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="810a5-104">会議ポリシーは、会議中にユーザーが利用できる機能 (会議とも呼ばれる) を定義します。</span><span class="sxs-lookup"><span data-stu-id="810a5-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="810a5-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="810a5-105">UI Reference</span></span>

<span data-ttu-id="810a5-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="810a5-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="810a5-107">**スコープ** 作成または変更する会議ポリシーのスコープ (グローバル、サイト、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="810a5-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="810a5-108">**名前** 各会議ポリシーには名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="810a5-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="810a5-109">グローバル会議ポリシーとサイト会議ポリシーの名前は既定で指定され、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="810a5-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="810a5-110">ユーザー会議ポリシーの場合は、ユーザーまたはユーザーのグループを識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="810a5-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="810a5-111">この名前は、会議ポリシーの保存後には変更できません。</span><span class="sxs-lookup"><span data-stu-id="810a5-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="810a5-112">**説明** このフィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="810a5-112">**Description** This field is optional.</span></span> <span data-ttu-id="810a5-113">会議ポリシーに関するその他の詳細を提供する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="810a5-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="810a5-114">**オーガナイザー ポリシー** このセクションの設定は、会議を開催するユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="810a5-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="810a5-115">設定が選択されている場合、ユーザーは、指定した特性を持つ会議を整理できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="810a5-116">設定が選択されていない場合、ユーザーは、この特性を持つ会議を整理できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="810a5-117">これらの設定では、他の会議の参加者としてユーザーがアクセスできるアクセス権は決めかねない。</span><span class="sxs-lookup"><span data-stu-id="810a5-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="810a5-118">セクションを開いたり閉じたりするには、ラベルの横にある上矢印および下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="810a5-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="810a5-119">**会議の最大サイズ** 会議で許可されるユーザーの最大数。</span><span class="sxs-lookup"><span data-stu-id="810a5-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="810a5-120">既定で、会議の最大サイズは 250 です。</span><span class="sxs-lookup"><span data-stu-id="810a5-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="810a5-121">**参加者に匿名ユーザーの招待を許可する** ユーザーが匿名ユーザーを会議に招待するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="810a5-122">匿名ユーザーとは、組織の Active Directory ドメイン サービスに資格情報を持たないユーザーであり、したがって認証されないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="810a5-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="810a5-123">**レコーディング** 参加者が会議を記録できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="810a5-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="810a5-124">オプションは None **または Enable** **recording です**。</span><span class="sxs-lookup"><span data-stu-id="810a5-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="810a5-125">**フェデレーション参加者と匿名参加者の記録を許可する** 外部および認証されていない参加者が会議を記録するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="810a5-126">**オーディオ/ビデオ** 参加者がオーディオとビデオを使用できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="810a5-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="810a5-127">**なし** オーディオとビデオの使用を防止するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="810a5-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="810a5-128">**IP オーディオを有効にする** ビデオではなくオーディオの使用を許可するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="810a5-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="810a5-129">**IP オーディオ/ビデオを有効にする** オーディオとビデオの両方を許可するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="810a5-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="810a5-130">**PSTN ダイヤルイン会議を有効にする** 音声/ビデオでオーディオ **を** 有効にした場合は、公衆交換電話網 (PSTN) を使用してユーザーが電話会議にダイヤルインできる場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="810a5-131">**匿名の参加者にダイヤルアウトを許可する** ユーザーが電話会議にダイヤルインを許可し、認証されていない (匿名の) ユーザーがダイヤルアウト電話を使用して会議に参加できる場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="810a5-132">会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="810a5-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="810a5-133">**ユーザーがダイヤルアウトエンタープライズ VoIP参加者を許可する** オーディオ/ビデオでオーディオ **を** 有効にした場合は、このチェック ボックスをオンにして、エンタープライズ VoIP が有効になっていないユーザーがダイヤルアウト 電話を使用して会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="810a5-134">電話会議サーバーをダイヤルアウトすると、ユーザーは電話をかけ、ユーザーは電話に応答して会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="810a5-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="810a5-135">**複数のビデオ ストリームを許可する** オーディオ/ビデオでビデオ **を有効に** した場合は、このチェック ボックスをオンにして、ユーザーがギャラリー ビュー ビデオを使用して会議を整理できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="810a5-136">このチェック ボックスをオンにすると、ユーザーは複数のビデオ ストリームを送信する会議を整理できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="810a5-137">このチェック ボックスがオンではない場合、ユーザーは単一のビデオ ストリームを送信する会議のみを整理できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="810a5-p110">このオプションによって、会議でサポートされるビデオ ストリームの種類が決まります。参加者が複数のビデオ ストリームを受信できるかどうかは、このオプションで決まりません。[**複数のビデオ ストリームでの参加を参加者に許可する**] オプションによって、参加者が複数のビデオ ストリームを受信できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="810a5-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="810a5-141">**データの共同作業** 会議でデータの共同作業を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="810a5-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="810a5-142">オプションは[なし **] または [\*\*\*\*データコラボレーションを有効にする] です**。</span><span class="sxs-lookup"><span data-stu-id="810a5-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="810a5-143">次の設定はデータのグループ作業に適用されます。</span><span class="sxs-lookup"><span data-stu-id="810a5-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="810a5-144">**フェデレーション参加者と匿名参加者にコンテンツのダウンロードを許可する** データの共同作業を許可する場合は、このチェック ボックスをオンにすると、外部および認証されていないユーザーは、スライドや資料などのコンテンツを会議からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="810a5-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="810a5-145">**参加者にファイルの転送を許可する** データの共同作業を許可する場合は、会議中にすべての参加者にファイル転送を許可するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="810a5-146">**注釈を有効にする** データの共同作業を許可する場合は、このチェック ボックスをオンにすると、参加者は会議中に共有されるコンテンツに対して画面の注釈を作成できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="810a5-147">**PowerPoint 注釈を有効にする** 注釈を許可する場合は、このチェック ボックスをオンにすると、参加者は会議中に PowerPoint スライドで注釈を共有できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="810a5-148">**ポーリングを有効にする** データの共同作業を許可する場合は、このチェック ボックスをオンにして、参加者が会議中にポーリングを保持できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="810a5-149">**アプリケーション共有** 会議でアプリケーション共有を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="810a5-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="810a5-150">オプションは、[アプリケーション共有 **を無効にする] または [\*\*\*\*アプリケーション共有を有効にする] です**。</span><span class="sxs-lookup"><span data-stu-id="810a5-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="810a5-151">次の設定はアプリケーション共有に適用されます。</span><span class="sxs-lookup"><span data-stu-id="810a5-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="810a5-152">**参加者に制御を許可する** アプリケーション共有を許可する場合は、このチェック ボックスをオンにして、参加者が会議中に共有されるアプリケーションまたはデスクトップを制御できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="810a5-153">**フェデレーション参加者と匿名参加者の制御を許可する** アプリケーション共有を許可する場合は、このチェック ボックスをオンにして、外部および認証されていない参加者が会議中に共有されるアプリケーションまたはデスクトップを制御できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="810a5-154">**参加者ポリシー** このセクションの設定は、会議または 2 者セッションの参加者としてユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="810a5-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="810a5-155">次の設定はユーザーごとの設定なので、会議または 2 者セッションの 1 人のユーザーが、同じ会議または 2 者セッションの別のユーザーとは異なる機能を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="810a5-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="810a5-156">セクションを開いたり閉じたりするには、ラベルの横にある上矢印および下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="810a5-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="810a5-p114">[**アプリケーションとデスクトップの共有を有効にする**] を選択すると、会議または 2 者間セッションへの参加中にユーザーにアプリケーションまたはデスクトップの共有が許可されます。[**アプリケーションとデスクトップの共有を無効にする**] を選択すると、会議または 2 者間セッションへの参加中にユーザーにアプリケーションまたはデスクトップの共有が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="810a5-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="810a5-159">**ピアツーピア ファイル転送を有効にする** このチェック ボックスをオンにすると、会議または 2 者間のセッション中に、ユーザー間のファイル転送 (つまり、すべての参加者が関与しないファイル転送) が許可されます。</span><span class="sxs-lookup"><span data-stu-id="810a5-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="810a5-160">**ピアツーピア録音を有効にする** ユーザーが 2 者間セッションを記録するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="810a5-161">**参加者が複数のビデオ ストリームに参加する** 参加者がそれを許可する会議でギャラリー ビュー ビデオを受信するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="810a5-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="810a5-162">このオプションを選択しない場合、参加者は会議で許可されているコンテンツに関係なく、1 つのビデオ ストリームのみを受信できます。</span><span class="sxs-lookup"><span data-stu-id="810a5-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="810a5-163">[**複数のビデオ ストリームを許可する**] は、会議で複数のビデオ ストリームを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="810a5-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="810a5-164">会議の機能の詳細については、「計画」のドキュメントの「[Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="810a5-164">For details about conferencing features and capabilities, see [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in the Planning documentation.</span></span> <span data-ttu-id="810a5-165">会議ポリシーの使用の詳細については、「操作」のドキュメントの「[Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="810a5-165">For details about working with conferencing policies, see [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in the Operations documentation.</span></span>