---
title: Education Insights へのユーザー アクセスを管理する
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams の Education Insights へのユーザー アクセスを管理します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145937"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="33255-103">Education Insights へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="33255-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="33255-104">このドキュメントでは、[Microsoft Teams の Education Insights](class-insights.md) へのユーザー アクセスを管理するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="33255-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="33255-105">教育リーダー、地区リーダー、学校長、学部長、カウンセラー、教科長、プログラム ディレクター、ソーシャル ワーカー、心理学者に許可を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="33255-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="33255-106">教職員には、クラス チームを所有している場合、*自動的* に許可が与えられます。</span><span class="sxs-lookup"><span data-stu-id="33255-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="33255-107">組織レベルの Insights を提供するには、[学生情報システム (SIS) からデータをインポートする](education-insights-sis-data-sync.md)必要があります。これは、Insights が教育システムの階層構造を正しくマッピングできるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="33255-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="33255-108">Insights へのユーザー アクセスを管理できるのはグローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="33255-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="33255-109">すべての教育リーダーに対して Insights を有効にして、各学校を理解するためのデータを入手し、問題をすばやく特定して教育者をサポートできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33255-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="33255-110">パイロットを実行している場合でも、すべての教育リーダーに対して Insights を有効にしておくと役立つ場合がありますが、コミュニケーションはパイロット グループのユーザーのみを対象とします。</span><span class="sxs-lookup"><span data-stu-id="33255-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="33255-111">アクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="33255-111">Grant permissions</span></span>

* <span data-ttu-id="33255-112">Insights アプリを開き、**[設定]** タブをクリックし、**[ユーザーのアクセス許可]** を選択する</span><span class="sxs-lookup"><span data-stu-id="33255-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="設定":::

* <span data-ttu-id="33255-114">**[ユーザーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33255-114">Select **Add users**.</span></span>
* <span data-ttu-id="33255-115">各ユーザーのユーザー名またはメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="33255-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="33255-116">アクセス許可レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="33255-116">Select the permission level:</span></span>
  * <span data-ttu-id="33255-117">**[すべての組織へのアクセス]** では、ユーザーはすべてのレベルのすべての組織単位を表示できます。</span><span class="sxs-lookup"><span data-stu-id="33255-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="33255-118">**[特定の学校へのアクセス]** では、ユーザーは選択した学校のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="33255-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="33255-119">入力を開始し、一覧から学校を選択します。</span><span class="sxs-lookup"><span data-stu-id="33255-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="33255-120">複数の学校をまとめて追加することができます。</span><span class="sxs-lookup"><span data-stu-id="33255-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="33255-121">**[新しいユーザーを追加する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33255-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="アクセス許可を付与する":::

> [!NOTE]
> <span data-ttu-id="33255-123">それらを必要とする教育リーダーとそのリーダーが担当する組織単位にのみ許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="33255-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="33255-124">特定の組織のユーザー許可が必要かどうかわからない場合は、法務担当者や人事担当者など、組織のプライバシーに関する専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="33255-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="33255-125">アクセス許可を編集する</span><span class="sxs-lookup"><span data-stu-id="33255-125">Edit permissions</span></span>
* <span data-ttu-id="33255-126">特定のユーザーを選び、**[アクセス許可の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33255-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="33255-127">アクセス許可レベルまたは学校の一覧を更新し、**[アクセス許可の更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33255-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="アクセス許可を編集する":::

## <a name="remove-permissions"></a><span data-ttu-id="33255-129">権限の削除</span><span class="sxs-lookup"><span data-stu-id="33255-129">Remove permissions</span></span>
* <span data-ttu-id="33255-130">削除するユーザーを選択し、**[ユーザーの削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33255-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="33255-131">これらのユーザーは、組織レベルの Insights にアクセスできなくなりますが、クラス チームを所有している場合は、クラス レベルの Insights にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="33255-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="アクセス許可を削除する":::
