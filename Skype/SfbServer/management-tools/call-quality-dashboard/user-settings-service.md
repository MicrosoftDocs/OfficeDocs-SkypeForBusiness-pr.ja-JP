---
title: 通話品質のダッシュ ボード (救難) のユーザー設定のサービス
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '概要: は、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部であるユーザー設定のサービスについて説明します。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 9e72d051699269b404d72e77ca00923b8ca240a3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293764"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="b4aea-104">通話品質のダッシュ ボード (救難) のユーザー設定のサービス</span><span class="sxs-lookup"><span data-stu-id="b4aea-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="b4aea-105">**の概要:** 品質のダッシュ ボードを呼び出すためのリポジトリ API の一部であるユーザー設定のサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b4aea-106">通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。</span><span class="sxs-lookup"><span data-stu-id="b4aea-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b4aea-107">ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。</span><span class="sxs-lookup"><span data-stu-id="b4aea-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="b4aea-108">ユーザー設定サービス</span><span class="sxs-lookup"><span data-stu-id="b4aea-108">User Settings Service</span></span>

<span data-ttu-id="b4aea-109">ユーザー設定は、アプリケーションの動作のユーザーごとのカスタマイズを含む、さまざまな目的のメタデータを格納するアプリケーションが使用できるキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="b4aea-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="b4aea-110">各ユーザーは、ユーザー設定のストレージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="b4aea-111">所有者だけは追加、変更、およびユーザー設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="b4aea-112">**グローバル設定**</span><span class="sxs-lookup"><span data-stu-id="b4aea-112">**Global Settings**</span></span>
  
<span data-ttu-id="b4aea-113">グローバル設定は、システムのユーザーが所有しているユーザー設定してすべてのユーザーに読み取り専用のアクセス。</span><span class="sxs-lookup"><span data-stu-id="b4aea-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="b4aea-114">グローバル設定は、定数: リポジトリの作成時に作成されると変更されません。</span><span class="sxs-lookup"><span data-stu-id="b4aea-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="b4aea-115">各ユーザーは、同じキーを使用してユーザー設定を作成することにより、グローバル設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="b4aea-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="b4aea-116">アプリケーションでは、効果的なユーザーの設定を要求すると、API は、それぞれグローバル設定のキーが同じである場合を優先する各ユーザーの設定と、ユーザーの設定とマージのグローバル設定のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="b4aea-117">API では、どの設定が上書きされることをアプリケーションが検索できるようにユーザー設定のみを返すこともします。</span><span class="sxs-lookup"><span data-stu-id="b4aea-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="b4aea-118">次の表には、他の操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4aea-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="b4aea-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="b4aea-119">**Operation**</span></span>|<span data-ttu-id="b4aea-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="b4aea-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b4aea-121">ユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="b4aea-122">ユーザー設定を取得、指定したユーザー設定の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="b4aea-123">ユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="b4aea-124">ユーザーの設定を返します。 1 つのユーザー設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b4aea-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

