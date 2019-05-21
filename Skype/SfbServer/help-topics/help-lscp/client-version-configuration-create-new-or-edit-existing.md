---
title: クライアントバージョンの構成新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。 グローバルクライアントバージョンの構成は、Skype for Business Server と共にインストールされ、サーバー展開全体でクライアントのバージョン管理を有効または無効にするために使用されます。 グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。 クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。
ms.openlocfilehash: 1a42f2a355ead1d98e7e8031b43db879f271dced
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300057"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="2dec9-106">クライアント バージョンの構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="2dec9-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="2dec9-107">クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="2dec9-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="2dec9-108">グローバルクライアントバージョンの構成は、Skype for Business Server と共にインストールされ、サーバー展開全体でクライアントのバージョン管理を有効または無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="2dec9-109">グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2dec9-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="2dec9-110">クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="2dec9-p103">サイト固有のクライアント バージョン構成を作成し、サイトごとにクライアント バージョンの制御を有効または無効にすることもできます。グローバル構成よりサイト固有の構成の方が優先されます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2dec9-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="2dec9-113">Tasks you can perform</span></span>

<span data-ttu-id="2dec9-114">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="2dec9-115">クライアント バージョン構成の名前を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="2dec9-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="2dec9-116">グローバルに、または特定のサイトについて、クライアント バージョン制御を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2dec9-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="2dec9-117">クライアント バージョン構成の既定のアクションを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="2dec9-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2dec9-118">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="2dec9-118">UI Reference</span></span>

<span data-ttu-id="2dec9-119">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="2dec9-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="2dec9-120">**スコープ**クライアントのバージョン構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="2dec9-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="2dec9-121">**名前**クライアントのバージョン構成の名前を追加または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="2dec9-122">**バージョン管理を有効にする**構成の範囲に応じて、グローバルに、またはサイトでクライアントのバージョン管理を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="2dec9-123">**既定のアクション**特定のクライアントのバージョンポリシーがないクライアントアプリケーションを使用してユーザーがログオンしようとしたときに適用される既定のアクションを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="2dec9-124">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2dec9-124">You have the following options:</span></span>

  - <span data-ttu-id="2dec9-125">**許可**クライアントバージョンがクライアントの [バージョンポリシー] リストのフィルターと一致しない場合、クライアントはログオンできます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="2dec9-126">**ブロック**クライアントバージョンがクライアントの [バージョンポリシー] リストのフィルターと一致しない場合に、クライアントがログオンできないようにします。</span><span class="sxs-lookup"><span data-stu-id="2dec9-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="2dec9-127">**URL が含まれるブロック**クライアントのバージョンがクライアントの [バージョンポリシー] リストのいずれのフィルターとも一致しない場合、クライアントはログオンできないようにし、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2dec9-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="2dec9-128">**URL で許可**クライアントバージョンがクライアントの [バージョンポリシー] リストのいずれのフィルターとも一致しない場合、クライアントはログオンでき、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="2dec9-129">**URL**[URL を含む**ブロック**] または [ **url で許可**] を選択した場合、エラーメッセージに含めるクライアントのダウンロード URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2dec9-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="2dec9-p105">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dec9-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

