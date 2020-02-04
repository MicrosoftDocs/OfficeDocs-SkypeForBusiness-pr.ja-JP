---
title: クライアント バージョンの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 環境でサポートするクライアントのバージョンを指定するだけでなく、バージョンポリシーが定義されていないクライアントに対する既定のアクションを指定することもできます。 これにより、使用している環境で使用するクライアントバージョンを制限することができます。これにより、複数のクライアントバージョンのサポートに関連するコストを制御することができます。
ms.openlocfilehash: d19eb77fd86020f01785ef77bd6651a83c748b55
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691572"
---
# <a name="client-version-configuration"></a><span data-ttu-id="cce7d-104">クライアント バージョンの構成</span><span class="sxs-lookup"><span data-stu-id="cce7d-104">Client Version Configuration</span></span>

<span data-ttu-id="cce7d-105">環境でサポートするクライアントのバージョンを指定するだけでなく、バージョンポリシーが定義されていないクライアントに対する既定のアクションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="cce7d-106">これにより、使用している環境で使用するクライアントバージョンを制限することができます。これにより、複数のクライアントバージョンのサポートに関連するコストを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cce7d-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="cce7d-107">Tasks you can perform</span></span>

<span data-ttu-id="cce7d-108">[**クライアントバージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="cce7d-109">既定の (**グローバル**) クライアントのバージョン構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="cce7d-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="cce7d-110">特定のサイトのクライアントバージョン構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="cce7d-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="cce7d-111">既存のクライアントバージョンの構成を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="cce7d-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="cce7d-112">匿名ユーザーはサイトに関連付けられていないため、匿名ユーザーはグローバルレベルポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cce7d-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="cce7d-113">UI Reference</span></span>

<span data-ttu-id="cce7d-114">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="cce7d-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="cce7d-115">**新規**特定のサイトのクライアントバージョン構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="cce7d-116">**編集**いずれかのクライアントのバージョンポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="cce7d-117">このオプションを使うと、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="cce7d-118">**詳細を表示**このオプションを選択すると、ダイアログボックスが開き、クライアントのバージョン構成のオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="cce7d-119">**すべて選択**このオプションでは、リスト内のすべてのクライアントバージョンの構成が選択されます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="cce7d-120">**削除**このオプションは、選択したすべてのクライアントバージョンの構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="cce7d-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="cce7d-121">**更新**クライアントのバージョン構成の一覧を更新して、すべてのクライアントのバージョン構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cce7d-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="cce7d-122">クライアントとクライアントバージョンの相互運用性の詳細については、「計画ドキュメントの[クライアントの相互運用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce7d-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="cce7d-123">クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cce7d-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

