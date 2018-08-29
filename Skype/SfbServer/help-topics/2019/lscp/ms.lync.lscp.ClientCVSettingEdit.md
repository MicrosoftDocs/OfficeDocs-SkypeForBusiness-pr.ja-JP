---
title: クライアント バージョンの構成を新規作成または既存の編集
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバル クライアント バージョンの構成では、ビジネス サーバーの Skype をインストールしを有効にするか、クライアントのバージョン管理サーバー全体の展開を無効にするために使用します。 グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。 クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。
ms.openlocfilehash: 6eacaddba90b123d04290640ebc8c0997e6904ce
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263493"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="0b340-106">クライアント バージョンの構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="0b340-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="0b340-107">クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0b340-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="0b340-108">グローバル クライアント バージョンの構成では、ビジネス サーバーの Skype をインストールしを有効にするか、クライアントのバージョン管理サーバー全体の展開を無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0b340-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="0b340-109">グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0b340-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="0b340-110">クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0b340-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="0b340-p103">サイト固有のクライアント バージョン構成を作成し、サイトごとにクライアント バージョンの制御を有効または無効にすることもできます。グローバル構成よりサイト固有の構成の方が優先されます。</span><span class="sxs-lookup"><span data-stu-id="0b340-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0b340-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="0b340-113">Tasks you can perform</span></span>

<span data-ttu-id="0b340-114">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0b340-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="0b340-115">クライアント バージョン構成の名前を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="0b340-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="0b340-116">グローバルに、または特定のサイトについて、クライアント バージョン制御を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="0b340-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="0b340-117">クライアント バージョン構成の既定のアクションを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="0b340-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0b340-118">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="0b340-118">UI Reference</span></span>

<span data-ttu-id="0b340-119">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="0b340-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="0b340-120">**スコープ**クライアント バージョンの構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="0b340-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="0b340-121">**名**追加したり、クライアント バージョンの構成の名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0b340-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="0b340-122">**バージョン管理を有効にします。** 有効にしたり、グローバルに、または構成のスコープに従って、サイトのクライアントのバージョン管理を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0b340-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="0b340-123">**既定のアクション**ユーザーが対象の特定のクライアント バージョン ポリシーがないクライアント アプリケーションを使用してログオンしようとするときに適用される既定のアクションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="0b340-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="0b340-124">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0b340-124">You have the following options:</span></span>

  - <span data-ttu-id="0b340-125">**許可します。** クライアントのバージョンがクライアント バージョン ポリシー] リストで、フィルターに一致しない場合、ログオンするクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b340-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="0b340-126">**ブロック**クライアントがクライアントのバージョンがクライアント バージョン ポリシー] リストで、フィルターに一致しない場合、ログオンするを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0b340-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="0b340-127">**URL のブロック**クライアントがクライアントのバージョンのクライアント バージョン ポリシー] ボックスの一覧で任意のフィルターと一致しないし、それ以降のクライアントをダウンロードできる URL を含むエラー メッセージが含まれて 場合にログオンするを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0b340-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="0b340-128">**URL を許可します。** それ以降のクライアントをダウンロードできる場所により、クライアントはログオンするクライアントのバージョンのクライアント バージョン ポリシー] ボックスの一覧で任意のフィルターと一致しないし、URL を含むエラー メッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b340-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="0b340-129">**URL****URL のブロック**または**URL を使用して許可する**を選択した場合は、エラー メッセージに含めるクライアントのダウンロード URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0b340-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="0b340-130">クライアントとクライアントのバージョン間での相互運用性に関する詳細については、計画ドキュメントの[クライアントの相互運用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b340-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0b340-131">クライアント バージョンの構成の操作に関する詳細については、操作マニュアルの[変更クライアントに明示的にサポートされていないまたは制限付きサイトの既定のアクション](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b340-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

