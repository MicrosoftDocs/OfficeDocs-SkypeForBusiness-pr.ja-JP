---
title: クライアント バージョン構成の作成(新規) または [既存の編集]
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバル クライアント バージョン構成は Skype for Business Server と一緒にインストールされ、サーバー展開全体のクライアント バージョン管理を有効または無効にするために使用されます。 グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。 クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。
ms.openlocfilehash: e42d2c9e6d06bc72cd64de148454d28aab41483d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812367"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="59ea4-106">クライアント バージョンの構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="59ea4-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="59ea4-107">クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="59ea4-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="59ea4-108">グローバル クライアント バージョン構成は Skype for Business Server と一緒にインストールされ、サーバー展開全体のクライアント バージョン管理を有効または無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="59ea4-109">グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="59ea4-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="59ea4-110">クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="59ea4-p103">サイト固有のクライアント バージョン構成を作成し、サイトごとにクライアント バージョンの制御を有効または無効にすることもできます。グローバル構成よりサイト固有の構成の方が優先されます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="59ea4-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="59ea4-113">Tasks you can perform</span></span>

<span data-ttu-id="59ea4-114">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="59ea4-115">クライアント バージョン構成の名前を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="59ea4-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="59ea4-116">グローバルに、または特定のサイトについて、クライアント バージョン制御を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="59ea4-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="59ea4-117">クライアント バージョン構成の既定のアクションを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="59ea4-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="59ea4-118">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="59ea4-118">UI Reference</span></span>

<span data-ttu-id="59ea4-119">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="59ea4-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="59ea4-120">**スコープ** クライアント バージョン構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="59ea4-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="59ea4-121">**名前** クライアント バージョン構成の名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="59ea4-122">**バージョン管理を有効にする** 構成のスコープに応じて、クライアント バージョン管理をグローバルに、またはサイトに対して有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="59ea4-123">**既定のアクション** ユーザーが特定のクライアント バージョン ポリシーがないクライアント アプリケーションを使用してログオンしようとするときに適用される既定のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="59ea4-124">以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="59ea4-124">You have the following options:</span></span>

  - <span data-ttu-id="59ea4-125">**許可** クライアント バージョンがクライアント バージョン ポリシーリストのフィルターと一致しない場合に、クライアントのログオンを許可します。</span><span class="sxs-lookup"><span data-stu-id="59ea4-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="59ea4-126">**ブロック** クライアント バージョンがクライアント バージョン ポリシーの一覧のフィルターと一致しない場合に、クライアントがログオンを許可しません。</span><span class="sxs-lookup"><span data-stu-id="59ea4-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="59ea4-127">**URL を使用したブロック** クライアント バージョンがクライアント バージョン ポリシーリストのフィルターと一致しない場合にクライアントがログオンし、新しいクライアントをダウンロードできる URL を含むエラー メッセージが含まれるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="59ea4-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="59ea4-128">**URL を使用して許可する** クライアント バージョンがクライアント バージョン ポリシーリストのフィルターと一致しない場合にクライアントのログオンを許可し、新しいクライアントをダウンロードできる URL を含むエラー メッセージを含む。</span><span class="sxs-lookup"><span data-stu-id="59ea4-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="59ea4-129">**URL**[URL 付きブロック] または **[URL** で許可] を選択した場合は、エラー メッセージに含めるクライアント ダウンロード URL を指定できます。 </span><span class="sxs-lookup"><span data-stu-id="59ea4-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="59ea4-130">クライアントとクライアント バージョン間の相互運用性の詳細については、「計画」のドキュメントの「 [クライアント](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) の相互運用性」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59ea4-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="59ea4-131">クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59ea4-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

