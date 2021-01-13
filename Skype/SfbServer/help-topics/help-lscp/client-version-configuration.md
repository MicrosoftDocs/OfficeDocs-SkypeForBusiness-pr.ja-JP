---
title: クライアント バージョンの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: 現在の環境でサポートするクライアントのバージョンのほか、バージョン ポリシーが定義されていないクライアントの既定のアクションも指定できます。これにより、現在の環境で使用するクライアント バージョンを制限し、複数のクライアント バージョンをサポートすることで発生するコストを制御できます。
ms.openlocfilehash: 3d821d9a31f70c0ea20342d48f28cc9ee14a2feb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829547"
---
# <a name="client-version-configuration"></a><span data-ttu-id="8d180-104">クライアント バージョンの構成</span><span class="sxs-lookup"><span data-stu-id="8d180-104">Client Version Configuration</span></span>

<span data-ttu-id="8d180-p102">現在の環境でサポートするクライアントのバージョンのほか、バージョン ポリシーが定義されていないクライアントの既定のアクションも指定できます。これにより、現在の環境で使用するクライアント バージョンを制限し、複数のクライアント バージョンをサポートすることで発生するコストを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8d180-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="8d180-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="8d180-107">Tasks you can perform</span></span>

<span data-ttu-id="8d180-108">[**クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d180-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="8d180-109">既定の (グローバル) **クライアント バージョン** の構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="8d180-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="8d180-110">特定のサイトのクライアント バージョン構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d180-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="8d180-111">既存のクライアント バージョン構成を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="8d180-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="8d180-112">匿名ユーザーをサイトに関連付けることはできないため、匿名ユーザーに適用されるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="8d180-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8d180-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="8d180-113">UI Reference</span></span>

<span data-ttu-id="8d180-114">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="8d180-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="8d180-115">**新規** 特定のサイトのクライアント バージョン構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8d180-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="8d180-116">**編集** 任意のクライアント バージョン ポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8d180-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="8d180-117">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d180-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="8d180-118">**詳細の表示** このオプションを選択すると、クライアント バージョン構成のオプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="8d180-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="8d180-119">**すべて選択** このオプションは、一覧内のすべてのクライアント バージョン構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d180-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="8d180-120">**Delete** このオプションでは、選択したクライアント バージョン構成はすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="8d180-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="8d180-121">**更新** クライアント バージョン構成リストを更新して、すべてのクライアント バージョン構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d180-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="8d180-122">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d180-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="8d180-123">クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d180-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

