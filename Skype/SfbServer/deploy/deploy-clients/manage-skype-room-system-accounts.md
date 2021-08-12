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
description: このトピックでは、ルーム システム アカウントを管理するSkype説明します。
ms.openlocfilehash: 416a211ec9954dd2c2a8c856a67c72226209f3e7dd6114536574e63c5520b841
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279465"
---
# <a name="manage-skype-room-system-accounts"></a>Skype Room System アカウントの管理
 
このトピックでは、ルーム システム アカウントを管理するSkype説明します。 

> [!NOTE]
> Microsoft Teams会議室は、依存関係と展開手順が異なる別の製品です。 会議室の詳細Microsoft Teams、会議室の管理Microsoft Teamsを[参照してください](/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>プール間Skypeルーム システム アカウントを移動する

Skype Room System アカウントをある Skype for Business Server プールから別の Skype for Business Server プールに移動する必要がある場合 (アップグレード時など)、次のコマンドを使用して、Skype Room System アカウント プールを移動します。 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>サービスのSkypeルーム システム アカウントをSkype for Businessする

Skype for Business Server プール上の Skype for Business サービスから既存の Skype Room System アカウントを無効にする必要がある場合は、次のコマンドを使用してアカウントを無効にします。 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>オプション: Active Directory で Skype Room System 管理者グループを作成する

ドメインSkypeする各ルーム システム クライアントは、ルーム システム アプライアンス PC 上のローカル管理者権限を持つドメイン ユーザー Skype管理できます。 したがって、Active Directory で専用の管理者グループを作成し、新しい管理者の Room System コンピューターのセットアップ中にこのグループSkype権限を与える必要があります。
