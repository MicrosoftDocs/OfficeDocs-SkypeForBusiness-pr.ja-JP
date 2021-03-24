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
description: Skype Room System アカウントを管理する方法については、このトピックを参照してください。
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093295"
---
# <a name="manage-skype-room-system-accounts"></a>Skype Room System アカウントの管理
 
Skype Room System アカウントを管理する方法については、このトピックを参照してください。 

> [!NOTE]
> Microsoft Teams Rooms は、依存関係と展開手順が異なる別の製品です。 Microsoft Teams Rooms の詳細については、「Microsoft Teams Rooms 管理の概要」を [参照してください](/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>プール間で Skype Room System アカウントを移動する

Skype Room System アカウントを 1 つの Skype for Business Server プールから別の Skype for Business Server プールに移動する必要がある場合 (アップグレード中など)、次のコマンドを使用して Skype Room System アカウント プールを移動します。 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Skype for Business サービスの Skype ルーム システム アカウントを無効にする

Skype for Business Server プールの Skype for Business サービスから既存の Skype Room System アカウントを無効にする必要がある場合は、次のコマンドを使用してアカウントを無効にします。 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>オプション: Active Directory で Skype Room System 管理者グループを作成する

ドメインに参加する各 Skype Room System クライアントは、Skype Room System アプライアンス PC 上のローカル管理者権限を持つドメイン ユーザーによって完全に管理できます。 そのため、Active Directory で専用の管理者グループを作成し、新しい Skype Room System コンピューターのセットアップ中にこのグループに管理者権限を与える必要があります。
