---
title: "Who に対するアクセス許可を構成する"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="82010-103">Who に対するアクセス許可を構成する</span><span class="sxs-lookup"><span data-stu-id="82010-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="82010-104">ユーザーは Microsoft Teams とともに Who アプリを使用して、質問をしたり、組織内のユーザーを、その仕事の内容や誰と働いているかに基づいて、検索したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="82010-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="82010-105">ユーザーが Who を最大限有効活用できるようにするには、Microsoft Graph で次のメンバー アクセス許可をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82010-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="82010-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="82010-106">Calendars.Read</span></span>

- <span data-ttu-id="82010-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="82010-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="82010-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="82010-108">Mail.Read</span></span>

- <span data-ttu-id="82010-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="82010-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="82010-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="82010-110">People.Read</span></span>

- <span data-ttu-id="82010-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="82010-111">People.Read.All</span></span>

- <span data-ttu-id="82010-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="82010-112">Sites.Read.All</span></span>

- <span data-ttu-id="82010-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="82010-113">User.Read.All</span></span>

<span data-ttu-id="82010-114">Microsoft Graph のアクセス許可の範囲の管理方法の詳細については、「[アクセス許可スコープ](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82010-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="82010-115">Microsoft Graph のアクセス許可の詳細については、「[Microsoft Graph のアクセス許可のリファレンス](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82010-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span></span>