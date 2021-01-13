---
title: Skype Room System アカウントの管理
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: このトピックでは、Skype Room System アカウントを管理する方法について説明します。
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805557"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="0bf4a-103">Skype Room System アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="0bf4a-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="0bf4a-104">このトピックでは、Skype Room System アカウントを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="0bf4a-105">Microsoft Teams Rooms は、依存関係と展開手順が異なる別の製品です。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="0bf4a-106">Microsoft Teams Rooms の詳細については、Microsoft Teams Rooms の管理の概要を [参照してください](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="0bf4a-107">Skype Room System アカウントをプール間で移動する</span><span class="sxs-lookup"><span data-stu-id="0bf4a-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="0bf4a-108">Skype Room System アカウントを 1 つの Skype for Business Server プールから別の Skype for Business Server プールに移動する必要がある場合 (アップグレード中など)、次のコマンドを使用して Skype Room System アカウント プールを移動します。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="0bf4a-109">Skype for Business サービスの Skype Room System アカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="0bf4a-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="0bf4a-110">Skype for Business Server プールの Skype for Business サービスから既存の Skype Room System アカウントを無効にする必要がある場合は、次のコマンドを使用してアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="0bf4a-111">オプション: Active Directory で Skype Room System 管理者グループを作成する</span><span class="sxs-lookup"><span data-stu-id="0bf4a-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="0bf4a-112">ドメインに参加する各 Skype Room System クライアントは、Skype Room System アプライアンス PC のローカル管理者権限を持つドメイン ユーザーによって完全に管理できます。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="0bf4a-113">したがって、Active Directory で専用の管理者グループを作成し、新しい Skype Room System コンピューターのセットアップ中にこのグループの管理者権限を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bf4a-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

