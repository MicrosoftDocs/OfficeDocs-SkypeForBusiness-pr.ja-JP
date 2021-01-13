---
title: 通話品質ダッシュボード (CQD) のユーザー設定サービス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部である User Settings Service について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803038"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="802d8-104">通話品質ダッシュボード (CQD) のユーザー設定サービス</span><span class="sxs-lookup"><span data-stu-id="802d8-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="802d8-105">**概要:** 通話品質ダッシュボードのリポジトリ API の一部である User Settings Service について説明します。</span><span class="sxs-lookup"><span data-stu-id="802d8-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="802d8-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="802d8-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="802d8-107">ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="802d8-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="802d8-108">ユーザー設定サービス</span><span class="sxs-lookup"><span data-stu-id="802d8-108">User Settings Service</span></span>

<span data-ttu-id="802d8-109">ユーザー設定は、アプリケーションがさまざまな目的でメタデータを格納するために使用できるキーと値のペアです。ユーザー単位でのアプリケーション動作のカスタマイズも含まれます。</span><span class="sxs-lookup"><span data-stu-id="802d8-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="802d8-110">各ユーザーは、ユーザー設定用の記憶域を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="802d8-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="802d8-111">ユーザー設定を追加、変更、削除できるのは所有者のみです。</span><span class="sxs-lookup"><span data-stu-id="802d8-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="802d8-112">**グローバル設定**</span><span class="sxs-lookup"><span data-stu-id="802d8-112">**Global Settings**</span></span>
  
<span data-ttu-id="802d8-113">グローバル設定は、システム ユーザーが所有するユーザー設定であり、すべてのユーザーが読み取り専用でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="802d8-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="802d8-114">グローバル設定は定数であり、リポジトリの作成時に作成され、変更されません。</span><span class="sxs-lookup"><span data-stu-id="802d8-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="802d8-115">各ユーザーは、同じキーでユーザー設定を作成することで、グローバル設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="802d8-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="802d8-116">アプリケーションが有効なユーザー設定を要求すると、API はユーザー設定とマージされた一連のグローバル設定を返し、キーが同じ場合は各ユーザー設定がそれぞれのグローバル設定に取って適用されます。</span><span class="sxs-lookup"><span data-stu-id="802d8-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="802d8-117">また、API はユーザー設定を返すだけで、どの設定が上書きされるのかアプリケーションが確認できます。</span><span class="sxs-lookup"><span data-stu-id="802d8-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="802d8-118">REST 操作を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="802d8-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="802d8-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="802d8-119">**Operation**</span></span>|<span data-ttu-id="802d8-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="802d8-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="802d8-121">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="802d8-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="802d8-122">ユーザー設定を取得すると、指定したユーザーの設定の一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="802d8-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="802d8-123">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="802d8-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="802d8-124">ユーザー設定を取得すると、1 つのユーザー設定が返されます。</span><span class="sxs-lookup"><span data-stu-id="802d8-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

