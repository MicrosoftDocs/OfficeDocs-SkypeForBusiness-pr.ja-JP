---
title: 通話品質ダッシュボードのユーザー設定サービス (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '概要: 通話品質ダッシュボードのリポジトリ API の一部である、ユーザー設定サービスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816646"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="32a28-104">通話品質ダッシュボードのユーザー設定サービス (CQD)</span><span class="sxs-lookup"><span data-stu-id="32a28-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="32a28-105">**概要:** 通話品質ダッシュボードのリポジトリ API の一部である、ユーザー設定サービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="32a28-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="32a28-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="32a28-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="32a28-107">ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="32a28-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="32a28-108">ユーザー設定サービス</span><span class="sxs-lookup"><span data-stu-id="32a28-108">User Settings Service</span></span>

<span data-ttu-id="32a28-109">ユーザー設定は、アプリケーション動作のカスタマイズなど、さまざまな目的のために、アプリケーションが使うことのできるキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="32a28-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="32a28-110">各ユーザーは、ユーザー設定のためのストレージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32a28-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="32a28-111">所有者のみが、ユーザー設定の追加、変更、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="32a28-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="32a28-112">**グローバル設定**</span><span class="sxs-lookup"><span data-stu-id="32a28-112">**Global Settings**</span></span>
  
<span data-ttu-id="32a28-113">グローバル設定とは、システムユーザーが所有するユーザー設定のことで、すべてのユーザーに読み取り専用のアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="32a28-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="32a28-114">グローバル設定は定数であり、リポジトリの作成時に作成され、変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="32a28-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="32a28-115">各ユーザーは、同じキーを使用してユーザー設定を作成することで、グローバル設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="32a28-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="32a28-116">アプリケーションが実効ユーザー設定を要求すると、API は、ユーザー設定と結合された一連のグローバル設定を返し、キーが同じである場合は、各ユーザー設定がそれぞれのグローバル設定を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="32a28-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="32a28-117">また、API では、アプリケーションがオーバーライドされた設定を確認できるように、ユーザー設定だけを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="32a28-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="32a28-118">REST 操作は、次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="32a28-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="32a28-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="32a28-119">**Operation**</span></span>|<span data-ttu-id="32a28-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="32a28-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="32a28-121">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="32a28-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="32a28-122">ユーザー設定の取得指定したユーザーの設定のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="32a28-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="32a28-123">ユーザー設定の取得</span><span class="sxs-lookup"><span data-stu-id="32a28-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="32a28-124">Get User Setting は、単一のユーザー設定を返します。</span><span class="sxs-lookup"><span data-stu-id="32a28-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

