---
title: Skype Room System アカウントを管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: このトピックでは、Skype Room System アカウントの管理方法について説明します。
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="d49d2-103">Skype Room System アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="d49d2-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="d49d2-104">このトピックでは、Skype Room System アカウントの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d49d2-104">Read this topic to learn how to manage Skype Room System accounts.</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="d49d2-105">Skype ルームのシステム アカウントをプール間で移動します。</span><span class="sxs-lookup"><span data-stu-id="d49d2-105">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="d49d2-106">Skype ルーム システム アカウント ビジネス サーバー プールの 1 つの Skype から別に移動 (たとえば、実行中にアップグレード) する場合は、Skype の部屋のシステム アカウントのプールに移動するのには次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d49d2-106">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="d49d2-107">ビジネス サービスの Skype の Skype ルームのシステム アカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d49d2-107">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="d49d2-108">Skype ルーム システムの既存のアカウント Skype からビジネス ・ サービス、Skype ビジネス サーバー プールの上を無効にする場合は、アカウントを無効にする次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d49d2-108">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="d49d2-109">オプション: Active Directory で Skype ルームのシステム管理者グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="d49d2-109">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="d49d2-110">各 Skype ルーム システム クライアントがドメインに参加するは、PC の Skype ルーム システム ・ アプライアンスのローカル管理者権限を持つドメイン ユーザーによって完全に管理できます。</span><span class="sxs-lookup"><span data-stu-id="d49d2-110">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="d49d2-111">したがって、Active Directory 内に専任の管理者のグループを作成して新しい Skype ルーム システム マシンのセットの中このグループの管理者権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="d49d2-111">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

