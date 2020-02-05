---
title: Skype Room System アカウントを管理する
ms.author: v-lanac
author: lanachin
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
description: このトピックでは、Skype Room System アカウントの管理方法について説明します。
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768660"
---
# <a name="manage-skype-room-system-accounts"></a>Skype Room System アカウントを管理する
 
このトピックでは、Skype Room System アカウントの管理方法について説明します。 

> [!NOTE]
> Microsoft Teams のルームは、依存関係と展開手順が異なるさまざまな製品です。 Microsoft Teams のルームの詳細については、「Microsoft Teams のルーム[管理の概要](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)」を参照してください。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>プール間で Skype Room System アカウントを移動する

Skype Room System アカウントを1つの Skype for Business サーバープールから別のプールに移動する必要がある場合 (たとえば、アップグレード中)、次のコマンドを使用して、Skype Room System アカウントプールを移動します。 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Skype for Business サービスの Skype Room System アカウントを無効にする

Skype for business Server プールの skype for Business サービスから既存の Skype Room システムアカウントを無効にする必要がある場合は、次のコマンドを使用してアカウントを無効にします。 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>オプション: Active Directory で Skype Room System 管理者グループを作成する

ドメインに参加している各 Skype Room システムクライアントは、Skype Room System アプライアンス PC のローカル管理者権限を持つドメインユーザによって完全に管理されます。 このため、新しい Skype Room システムマシンのセットアップ中に、このグループに管理者権限を与えることができます。
  

