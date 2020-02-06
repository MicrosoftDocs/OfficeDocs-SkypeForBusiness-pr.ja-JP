---
title: 会議の構成新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。 これらの設定は、スケジュールされている会議にのみ適用されます。 これらの設定は、クライアントで [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。
ms.openlocfilehash: 7c86415d08d2b48d542334ac74bc1316102e592d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796316"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="70f80-105">会議構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="70f80-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="70f80-p102">会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。これらの設定は、スケジュールされている会議にのみ適用されます。クライアントの [**今すぐミーティング**] オプションをクリックして作成されるアドホック会議には適用されません。</span><span class="sxs-lookup"><span data-stu-id="70f80-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="70f80-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="70f80-109">UI Reference</span></span>

<span data-ttu-id="70f80-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="70f80-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="70f80-111">**スコープ**作成または変更する会議の構成の範囲を指定します。グローバル、サイト、またはプール。</span><span class="sxs-lookup"><span data-stu-id="70f80-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="70f80-112">**名前**会議の構成には既定で名前が付けられており、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="70f80-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="70f80-113">**PSTN の発信**者がロビーをバイパスするこのチェックボックスをオンにすると、電話会議にダイヤルインしているユーザーが公衆交換電話網 (PSTN) の電話回線を使って自動的に会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="70f80-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="70f80-114">その場合、発信者は、会議の発表者によって会議へのアクセスが許可されるまで、保留状態のまま電話会議ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="70f80-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="70f80-115">**プレゼンターとして指定**会議の開催者として自動的に指定されたユーザーのカテゴリ (会議の開催者以外) を選択します。</span><span class="sxs-lookup"><span data-stu-id="70f80-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="70f80-116">この設定に関係なく、会議がスケジュールされているときに発表者に明示的に指定することも、会議中に明示的に発表者に昇格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="70f80-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="70f80-117">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="70f80-117">The options are:</span></span>

  - <span data-ttu-id="70f80-118">**なし**開催者以外の人が自動的に発表者として指定されない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="70f80-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="70f80-119">**会社**組織のメンバーのみを発表者として自動的に指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="70f80-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="70f80-120">**すべてのユーザー**すべての参加者を発表者に自動的に指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="70f80-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="70f80-121">**既定で割り当てられた会議の種類**この設定では、Outlook 会議のアドインが開催者の割り当てられた会議を使用して常に会議をスケジュールするかどうかを制御します。つまり、スケジュールされた会議の参加 URL と音声情報は常に同じです。</span><span class="sxs-lookup"><span data-stu-id="70f80-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="70f80-122">このチェック ボックスをオンにすると、スケジュールされる会議には常に同じ参加 URL が与えられます。</span><span class="sxs-lookup"><span data-stu-id="70f80-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="70f80-123">このチェック ボックスをオフにすると、会議ごとに異なる参加 URL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="70f80-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="70f80-124">**既定で匿名ユーザーを許可**する匿名 (認証されていない) ユーザーが既定で会議に参加することを許可されている場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="70f80-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="70f80-125">匿名ユーザーが既定で会議に参加することを許可されていない場合は、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="70f80-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="70f80-126">**ロゴ URL**ユーザー設定の会議出席依頼に使用する画像が含まれている URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="70f80-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="70f80-127">**ヘルプ URL**ユーザーが会議に参加するためのサポートを取得できる web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="70f80-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="70f80-128">**法的テキスト URL**会議の法的情報と免責事項を含む web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="70f80-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="70f80-129">**ユーザー設定のフッターテキスト**ユーザー設定の会議出席依頼に使用するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="70f80-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="70f80-p107">会議構成の使用の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)」を参照してください。大規模ミーティングの会議構成の設定については、「計画」のドキュメントの「[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f80-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


