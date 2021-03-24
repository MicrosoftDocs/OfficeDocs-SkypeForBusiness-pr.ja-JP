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
ms.openlocfilehash: 31facafd00a25993aa16f5d89b1fad5a97e566a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095621"
---
# <a name="client-version-configuration"></a><span data-ttu-id="852b2-104">クライアント バージョンの構成</span><span class="sxs-lookup"><span data-stu-id="852b2-104">Client Version Configuration</span></span>

<span data-ttu-id="852b2-p102">現在の環境でサポートするクライアントのバージョンのほか、バージョン ポリシーが定義されていないクライアントの既定のアクションも指定できます。これにより、現在の環境で使用するクライアント バージョンを制限し、複数のクライアント バージョンをサポートすることで発生するコストを制御できます。</span><span class="sxs-lookup"><span data-stu-id="852b2-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="852b2-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="852b2-107">Tasks you can perform</span></span>

<span data-ttu-id="852b2-108">[**クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="852b2-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="852b2-109">既定の (グローバル) **クライアント** バージョンの構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="852b2-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="852b2-110">特定のサイトのクライアント バージョン構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="852b2-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="852b2-111">既存のクライアント バージョン構成を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="852b2-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="852b2-112">匿名ユーザーをサイトに関連付けることはできないため、匿名ユーザーに適用されるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="852b2-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="852b2-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="852b2-113">UI Reference</span></span>

<span data-ttu-id="852b2-114">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="852b2-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="852b2-115">**New** 特定のサイトのクライアント バージョン構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="852b2-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="852b2-116">**編集** クライアント バージョン ポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="852b2-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="852b2-117">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="852b2-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="852b2-118">**詳細の表示** このオプションは、クライアント バージョン構成のオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="852b2-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="852b2-119">**[すべて選択]** このオプションは、リスト内のすべてのクライアント バージョン構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="852b2-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="852b2-120">**削除** このオプションは、選択したクライアント バージョン構成をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="852b2-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="852b2-121">**更新** クライアント バージョン構成リストを更新して、すべてのクライアント バージョン構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="852b2-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="852b2-122">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="852b2-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="852b2-123">クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="852b2-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>