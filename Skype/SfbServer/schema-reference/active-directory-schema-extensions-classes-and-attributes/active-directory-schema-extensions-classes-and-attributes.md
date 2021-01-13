---
title: アクティブなディレクトリ スキーマの拡張機能、クラスおよび属性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: このリファレンス セクションの内容は、次のとおりです。
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831937"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="87661-103">アクティブなディレクトリ スキーマの拡張機能、クラスおよび属性</span><span class="sxs-lookup"><span data-stu-id="87661-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="87661-104">このリファレンス セクションの内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87661-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="87661-105">Skype for Business Server 用に新規または変更された Active Directory スキーマ拡張機能</span><span class="sxs-lookup"><span data-stu-id="87661-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="87661-106">Active Directory スキーマには、Active Directory フォレスト内に作成できるすべてのオブジェクト クラスの正式な定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="87661-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="87661-107">このスキーマには、Active Directory オブジェクトに存在できるすべての属性の正式な定義も含まれます。</span><span class="sxs-lookup"><span data-stu-id="87661-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="87661-108">Active Directory グローバル カタログには、フォレストのすべてのオブジェクトのレプリカと、各オブジェクトの属性のサブセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="87661-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="87661-109">このセクションでは、Skype for Business Server で新規または変更されたクラスと属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="87661-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="87661-110">各クラスの説明を含む、Skype for Business Server で使用されるクラスすべて</span><span class="sxs-lookup"><span data-stu-id="87661-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="87661-111">Skype for Business Server で使用される属性すべて(各属性の説明付き)</span><span class="sxs-lookup"><span data-stu-id="87661-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="87661-112">Skype for Business Server で使用されるクラスの一覧。各クラスには、次の属性が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="87661-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="87661-113">グローバル設定とオブジェクト、およびフォレストの準備中に作成されたユニバーサル サービス グループとユニバーサル管理グループ</span><span class="sxs-lookup"><span data-stu-id="87661-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="87661-114">ドメインの準備中にドメイン ルートおよび組み込みコンテナーに作成されたアクセス制御エントリ (ACE)</span><span class="sxs-lookup"><span data-stu-id="87661-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="87661-115">Grant_CsSetupPermission コマンドレットによって Active Directory の組織単位 (OU) に対して行われる変更</span><span class="sxs-lookup"><span data-stu-id="87661-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="87661-116">Grant_CsOUPermission コマンドレットによって Active Directory の OU に対して行われる変更</span><span class="sxs-lookup"><span data-stu-id="87661-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="87661-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="87661-117">In This Section</span></span>

- [<span data-ttu-id="87661-118">Skype for Business Server でのスキーマの変更点</span><span class="sxs-lookup"><span data-stu-id="87661-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="87661-119">Skype for Business Server のスキーマ クラスと説明</span><span class="sxs-lookup"><span data-stu-id="87661-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="87661-120">Skype for Business Server のスキーマ属性と説明</span><span class="sxs-lookup"><span data-stu-id="87661-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="87661-121">Skype for Business Server のクラス別のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="87661-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="87661-122">Skype for Business Server でのフォレストの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="87661-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="87661-123">Skype for Business Server でのドメインの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="87661-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="87661-124">Skype for Business Server Grant-CsSetupPermissionによって行われた変更</span><span class="sxs-lookup"><span data-stu-id="87661-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="87661-125">Skype for Business Server Grant-CsOUPermissionによって行われた変更</span><span class="sxs-lookup"><span data-stu-id="87661-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

