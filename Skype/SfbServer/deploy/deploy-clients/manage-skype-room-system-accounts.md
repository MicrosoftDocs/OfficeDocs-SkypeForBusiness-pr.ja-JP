---
title: Skype Room System アカウントを管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: このトピックでは、Skype Room System アカウントの管理方法について説明します。
ms.openlocfilehash: 4c276d4acf0cf15df7689fa5c11a0e6e2cde785b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212622"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="5f550-103">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="5f550-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="5f550-104">このトピックでは、Skype Room System アカウントの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f550-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="5f550-105">マイクロソフト チームの会議室は、さまざまな依存関係および展開の手順で別の製品です。</span><span class="sxs-lookup"><span data-stu-id="5f550-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="5f550-106">マイクロソフト チームの会議室については、マイクロソフト チームの会議室の[管理の概要](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f550-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="5f550-107">Skype ルームのシステム アカウントをプール間で移動します。</span><span class="sxs-lookup"><span data-stu-id="5f550-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="5f550-108">Skype ルーム システム アカウント ビジネス サーバー プールの 1 つの Skype から別に移動 (たとえば、実行中にアップグレード) する場合は、Skype の部屋のシステム アカウントのプールに移動するのには次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f550-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="5f550-109">ビジネス サービスの Skype の Skype ルームのシステム アカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5f550-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="5f550-110">Skype ルーム システムの既存のアカウント Skype からビジネス ・ サービス、Skype ビジネス サーバー プールの上を無効にする場合は、アカウントを無効にする次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f550-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="5f550-111">オプション: Active Directory で Skype ルームのシステム管理者グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f550-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="5f550-112">各 Skype ルーム システム クライアントがドメインに参加するは、PC の Skype ルーム システム ・ アプライアンスのローカル管理者権限を持つドメイン ユーザーによって完全に管理できます。</span><span class="sxs-lookup"><span data-stu-id="5f550-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="5f550-113">したがって、Active Directory 内に専任の管理者のグループを作成して新しい Skype ルーム システム マシンのセットの中このグループの管理者権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="5f550-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

