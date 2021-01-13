---
title: 会議の構成の作成 (新規) または [既存の編集]
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。 これらの設定は、スケジュールされている会議にのみ適用されます。 クライアントの [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。
ms.openlocfilehash: 87d07100e7f9411f139711de3302ce384e71cb01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824817"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="92d46-105">会議の構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="92d46-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="92d46-106">会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="92d46-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="92d46-107">これらの設定は、スケジュールされている会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="92d46-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="92d46-108">クライアントの [今すぐミーティング] オプションをクリックして作成された臨時の **会議には適用** されません。</span><span class="sxs-lookup"><span data-stu-id="92d46-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="92d46-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="92d46-109">UI Reference</span></span>

<span data-ttu-id="92d46-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="92d46-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="92d46-111">**スコープ** 作成または変更する会議構成のスコープ (グローバル、サイト、またはプール) を識別します。</span><span class="sxs-lookup"><span data-stu-id="92d46-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="92d46-112">**名前** 会議の構成には既定で名前が付けられたので、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="92d46-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="92d46-113">**PSTN 発信者がロビーをバイパスする** 公衆交換電話網 (PSTN) 電話回線を使用して会議にダイヤルインするユーザーを自動的に許可するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="92d46-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="92d46-114">その場合、発信者は、会議の発表者によって会議へのアクセスが許可されるまで、保留状態のまま電話会議ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="92d46-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="92d46-115">**発表者として指定する** 会議に参加するときに発表者として自動的に指定されるユーザーのカテゴリ (会議の開催者以外) を選択します。</span><span class="sxs-lookup"><span data-stu-id="92d46-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="92d46-116">この設定に関係なく、会議のスケジュール時に発表者を明示的に指定するか、会議中に明示的に発表者に昇格することができます。</span><span class="sxs-lookup"><span data-stu-id="92d46-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="92d46-117">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="92d46-117">The options are:</span></span>

  - <span data-ttu-id="92d46-118">**なし** 開催者以外のユーザーが発表者として自動的に指定される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92d46-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="92d46-119">**会社** 組織のメンバーのみを発表者として自動的に指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92d46-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="92d46-120">**すべてのユーザー** すべてのユーザーを発表者に自動的に指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92d46-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="92d46-121">**既定で割り当てられた会議の種類** この設定は、Outlook 会議アドインが常に開催者の割り当てられた会議を使用して会議をスケジュールするかどうかを制御します。つまり、スケジュールされた会議は常に同じ参加 URL とオーディオ情報を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d46-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="92d46-122">このチェック ボックスをオンにすると、スケジュールされる会議には常に同じ参加 URL が与えられます。</span><span class="sxs-lookup"><span data-stu-id="92d46-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="92d46-123">このチェック ボックスをオフにすると、会議ごとに異なる参加 URL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="92d46-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="92d46-124">**匿名ユーザーを既定で許可する** 匿名 (認証されていない) ユーザーが既定で会議に出席できる場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="92d46-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="92d46-125">匿名ユーザーが既定で会議に出席できない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="92d46-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="92d46-126">**ロゴ URL** カスタム会議出席依頼に使用するイメージを含む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d46-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="92d46-127">**ヘルプ URL** ユーザーが会議に参加するサポートを得る Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d46-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="92d46-128">**法的なテキスト URL** 会議の法的情報と免責事項を含む Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d46-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="92d46-129">**カスタム フッター テキスト** カスタム会議出席依頼に使用するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="92d46-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="92d46-130">会議の構成の操作の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d46-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="92d46-131">大規模ミーティングの会議構成の設定については、「計画」のドキュメントの「[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d46-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


