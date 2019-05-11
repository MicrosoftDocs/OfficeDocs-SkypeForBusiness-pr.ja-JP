---
title: 会議設定の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。 これらの設定は、スケジュールされている会議にのみ適用されます。 これらの設定は、クライアントで [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。
ms.openlocfilehash: 6af03588f5265c7fba208e88f2965639a1933153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910891"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="a3876-105">会議構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="a3876-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="a3876-p102">会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。これらの設定は、スケジュールされている会議にのみ適用されます。クライアントの [**今すぐミーティング**] オプションをクリックして作成されるアドホック会議には適用されません。</span><span class="sxs-lookup"><span data-stu-id="a3876-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a3876-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="a3876-109">UI Reference</span></span>

<span data-ttu-id="a3876-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="a3876-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a3876-111">**スコープ**作成または変更する会議の構成のスコープを識別します。 グローバル、サイト、またはプール。</span><span class="sxs-lookup"><span data-stu-id="a3876-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="a3876-112">**名**会議の構成が既定では、名前付きし、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3876-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="a3876-113">**PSTN の呼び出し元はロビーをバイパス**公衆交換電話網 (PSTN) 電話回線経由で会議にダイヤルイン ユーザーを自動的に認める場合は、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3876-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="a3876-114">その場合、発信者は、会議の発表者によって会議へのアクセスが許可されるまで、保留状態のまま電話会議ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="a3876-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="a3876-115">**発表者として指定**(会議の開催者) だけでなく、会議に参加するときに自動的に、発表者として指定されたユーザーのカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3876-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="a3876-116">この設定では、発表者が明示的に時に指定できる発表者として会議をスケジュールすると、または会議中に明示的に発表者に昇格することができます。</span><span class="sxs-lookup"><span data-stu-id="a3876-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="a3876-117">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a3876-117">The options are:</span></span>

  - <span data-ttu-id="a3876-118">**なし**開催者以外の誰が自動的に発表者として指定されている場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3876-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="a3876-119">**会社**自動的に発表者として、組織のメンバーのみを指定するのにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3876-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="a3876-120">**全員**発表のすべてのユーザーを自動的に指定するのにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3876-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="a3876-121">**既定で割り当てられた会議の種類**この設定で制御するかどうか、Outlook の会議アドイン常にスケジュール会議開催者を使用して会議を割り当てられている、同じ結合 URL とオーディオについて常に会議をスケジュールすることを意味であります。</span><span class="sxs-lookup"><span data-stu-id="a3876-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="a3876-122">このチェック ボックスをオンにすると、スケジュールされる会議には常に同じ参加 URL が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a3876-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="a3876-123">このチェック ボックスをオフにすると、会議ごとに異なる参加 URL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3876-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="a3876-124">**既定で匿名ユーザーを Admit**このチェック ボックスを選択するかどうかは匿名 (つまり、認証されていない) 既定で会議への参加を許可されています。</span><span class="sxs-lookup"><span data-stu-id="a3876-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="a3876-125">匿名ユーザーが、既定で会議への参加を許可されていない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a3876-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="a3876-126">**ロゴの URL**カスタム会議出席依頼に使用するイメージの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3876-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="a3876-127">**URL のヘルプ**ユーザーが会議に参加するための支援を取得できる web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3876-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="a3876-128">**法的テキストの URL**法務情報のある web サイトの URL は、会議の免責事項を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3876-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="a3876-129">**カスタム フッターのテキスト**カスタム会議出席依頼で使用するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3876-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="a3876-p107">会議構成の使用の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)」を参照してください。大規模ミーティングの会議構成の設定については、「計画」のドキュメントの「[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3876-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


