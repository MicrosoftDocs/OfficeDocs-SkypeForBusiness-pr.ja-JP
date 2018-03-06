---
title: "Who に対するアクセス許可を構成する"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 629a732b178f6702f5ba308c6d0effe069019091
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="575a0-103">Who に対するアクセス許可を構成する</span><span class="sxs-lookup"><span data-stu-id="575a0-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="575a0-104">ユーザーは Microsoft Teams とともに Who アプリを使用して、質問をしたり、組織内のユーザーを、その仕事の内容や誰と働いているかに基づいて、検索したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="575a0-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="575a0-105">ユーザーが Who を最大限有効活用できるようにするには、Microsoft Graph で次のメンバー アクセス許可をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="575a0-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="575a0-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="575a0-106">Calendars.Read</span></span>

- <span data-ttu-id="575a0-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="575a0-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="575a0-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="575a0-108">Mail.Read</span></span>

- <span data-ttu-id="575a0-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="575a0-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="575a0-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="575a0-110">People.Read</span></span>

- <span data-ttu-id="575a0-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="575a0-111">People.Read.All</span></span>

- <span data-ttu-id="575a0-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="575a0-112">Sites.Read.All</span></span>

- <span data-ttu-id="575a0-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="575a0-113">User.Read.All</span></span>

<span data-ttu-id="575a0-114">Microsoft Graph のアクセス許可の範囲の管理方法の詳細については、「[アクセス許可スコープ](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="575a0-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="575a0-115">Microsoft Graph のアクセス許可の詳細については、「[Microsoft Graph のアクセス許可のリファレンス](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="575a0-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>