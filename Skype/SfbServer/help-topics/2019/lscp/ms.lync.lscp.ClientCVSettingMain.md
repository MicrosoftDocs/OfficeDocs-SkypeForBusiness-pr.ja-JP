---
title: クライアント バージョンの構成
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 環境内でサポートするクライアントのバージョンを指定するだけでなく、バージョン ポリシーを定義していないクライアントの既定のアクションを指定することも。 これにより、お客様の環境では、複数のクライアント バージョンのサポートに伴うコストを制御することができますで使用するクライアント バージョンを制限することができます。
ms.openlocfilehash: c83dc832d6ea866a7f29f0a98213ea25853cd2f7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879841"
---
# <a name="client-version-configuration"></a><span data-ttu-id="f4027-104">クライアント バージョンの構成</span><span class="sxs-lookup"><span data-stu-id="f4027-104">Client Version Configuration</span></span>

<span data-ttu-id="f4027-105">環境内でサポートするクライアントのバージョンを指定するだけでなく、バージョン ポリシーを定義していないクライアントの既定のアクションを指定することも。</span><span class="sxs-lookup"><span data-stu-id="f4027-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="f4027-106">これにより、お客様の環境では、複数のクライアント バージョンのサポートに伴うコストを制御することができますで使用するクライアント バージョンを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="f4027-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f4027-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="f4027-107">Tasks you can perform</span></span>

<span data-ttu-id="f4027-108">**クライアント バージョンの構成**] ページで、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4027-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="f4027-109">(**グローバル**) の既定のクライアント バージョンの構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="f4027-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="f4027-110">特定のサイトのクライアント バージョンの構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="f4027-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="f4027-111">有効にして、既存のクライアント バージョンの構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f4027-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="f4027-112">匿名ユーザーがサイトに関連付けられていないため、グローバル レベルのポリシーだけでは匿名ユーザーが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="f4027-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f4027-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="f4027-113">UI Reference</span></span>

<span data-ttu-id="f4027-114">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="f4027-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="f4027-115">**新しい**特定のサイトのクライアント バージョンの構成を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f4027-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="f4027-116">**編集**クライアント バージョン ポリシーのいずれかのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f4027-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="f4027-117">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="f4027-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="f4027-118">**詳細を表示します。** このオプションは、クライアント バージョンの構成のオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4027-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="f4027-119">**すべてを選択**このオプションでは、一覧のすべてのクライアント バージョンの構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4027-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="f4027-120">**削除**このオプションは、選択したクライアントのバージョンのすべての構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="f4027-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="f4027-121">**更新**クライアント バージョンの構成] ボックスの一覧のすべてのクライアント バージョンの構成オプションの状態を確認するのにを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="f4027-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="f4027-122">クライアントとクライアントのバージョン間での相互運用性に関する詳細については、計画ドキュメントの[クライアントの相互運用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4027-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="f4027-123">クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4027-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

