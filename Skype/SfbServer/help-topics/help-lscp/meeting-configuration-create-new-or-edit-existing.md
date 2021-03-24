---
title: 会議の構成 新規の作成または既存の編集
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
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。 これらの設定は、スケジュールされている会議にのみ適用されます。 クライアントで [今すぐ会議] オプションをクリックして作成されたアドホック会議には適用されません。
ms.openlocfilehash: 21cc12cd025edfc573e1e2f21ed08181f1a0c926
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099673"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="29a44-105">会議の構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="29a44-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="29a44-106">会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="29a44-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="29a44-107">これらの設定は、スケジュールされている会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="29a44-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="29a44-108">クライアントで [今すぐ会議] オプションをクリックして作成されたアドホック **会議には適用** されません。</span><span class="sxs-lookup"><span data-stu-id="29a44-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="29a44-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="29a44-109">UI Reference</span></span>

<span data-ttu-id="29a44-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="29a44-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="29a44-111">**スコープ** 作成または変更する会議構成のスコープ (グローバル、サイト、またはプール) を識別します。</span><span class="sxs-lookup"><span data-stu-id="29a44-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="29a44-112">**名前** 会議の構成は既定で名前が付け、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="29a44-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="29a44-113">**PSTN 発信者がロビーをバイパスする** 公衆交換電話網 (PSTN) 電話回線を使用して会議にダイヤルインしているユーザーを自動的に許可するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29a44-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="29a44-114">その場合、発信者は、会議の発表者によって会議へのアクセスが許可されるまで、保留状態のまま電話会議ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="29a44-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="29a44-115">**発表者として指定する** 会議に参加するときに自動的に発表者として指定されるユーザーのカテゴリ (会議の開催者以外) を選択します。</span><span class="sxs-lookup"><span data-stu-id="29a44-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="29a44-116">この設定に関係なく、会議のスケジュール時に発表者を明示的に発表者として指定するか、会議中に発表者に明示的に昇格できます。</span><span class="sxs-lookup"><span data-stu-id="29a44-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="29a44-117">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="29a44-117">The options are:</span></span>

  - <span data-ttu-id="29a44-118">**なし** 開催者以外のユーザーが発表者として自動的に指定しない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="29a44-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="29a44-119">**会社** 組織のメンバーのみを発表者として自動的に指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="29a44-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="29a44-120">**すべてのユーザー** 発表者になるユーザーを自動的に指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="29a44-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="29a44-121">**既定で割り当てられた会議の種類** この設定は、Outlook Conferenceing Addin が常に開催者の割り当てられた会議を使用して会議をスケジュールするかどうかを制御します。つまり、スケジュールされた会議には常に同じ参加 URL と音声情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="29a44-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="29a44-122">このチェック ボックスをオンにすると、スケジュールされる会議には常に同じ参加 URL が与えられます。</span><span class="sxs-lookup"><span data-stu-id="29a44-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="29a44-123">このチェック ボックスをオフにすると、会議ごとに異なる参加 URL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="29a44-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="29a44-124">**既定で匿名ユーザーを許可する** 匿名 (つまり、認証されていない) ユーザーが既定で会議に出席できる場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29a44-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="29a44-125">匿名ユーザーが既定で会議に出席できない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="29a44-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="29a44-126">**ロゴ URL** カスタム会議の招待に使用するイメージを含む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="29a44-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="29a44-127">**ヘルプ URL** ユーザーが会議への参加を支援できる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="29a44-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="29a44-128">**法的なテキスト URL** 会議の法的情報と免責事項を含む Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="29a44-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="29a44-129">**カスタム フッター テキスト** カスタム会議出席依頼で使用するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="29a44-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="29a44-130">会議の構成の操作の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a44-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span> <span data-ttu-id="29a44-131">大規模ミーティングの会議構成の設定については、「計画」のドキュメントの「[Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a44-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) in the Planning documentation.</span></span>