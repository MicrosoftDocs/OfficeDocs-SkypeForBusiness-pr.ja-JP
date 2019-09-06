---
title: Skype Room System アカウントを管理する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: このトピックでは、Skype Room System アカウントの管理方法について説明します。
ms.openlocfilehash: ab82780617ba8fc6304bb97f56a319c7898bff44
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774897"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="58a85-103">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="58a85-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="58a85-104">このトピックでは、Skype Room System アカウントの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58a85-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="58a85-105">Microsoft Teams のルームは、依存関係と展開手順が異なるさまざまな製品です。</span><span class="sxs-lookup"><span data-stu-id="58a85-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="58a85-106">Microsoft Teams のルームの詳細については、「Microsoft Teams のルーム[管理の概要](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a85-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="58a85-107">プール間で Skype Room System アカウントを移動する</span><span class="sxs-lookup"><span data-stu-id="58a85-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="58a85-108">Skype Room System アカウントを1つの Skype for Business サーバープールから別のプールに移動する必要がある場合 (たとえば、アップグレード中)、次のコマンドを使用して、Skype Room System アカウントプールを移動します。</span><span class="sxs-lookup"><span data-stu-id="58a85-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="58a85-109">Skype for Business サービスの Skype Room System アカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="58a85-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="58a85-110">Skype for business Server プールの skype for Business サービスから既存の Skype Room システムアカウントを無効にする必要がある場合は、次のコマンドを使用してアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="58a85-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="58a85-111">オプション: Active Directory で Skype Room System 管理者グループを作成する</span><span class="sxs-lookup"><span data-stu-id="58a85-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="58a85-112">ドメインに参加している各 Skype Room システムクライアントは、Skype Room System アプライアンス PC のローカル管理者権限を持つドメインユーザによって完全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="58a85-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="58a85-113">このため、新しい Skype Room システムマシンのセットアップ中に、このグループに管理者権限を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="58a85-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

