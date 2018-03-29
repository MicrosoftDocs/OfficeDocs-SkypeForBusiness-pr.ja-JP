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
# <a name="manage-skype-room-system-accounts"></a>Skype Room System アカウントを管理する
 
このトピックでは、Skype Room System アカウントの管理方法について説明します。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Skype ルームのシステム アカウントをプール間で移動します。

Skype ルーム システム アカウント ビジネス サーバー プールの 1 つの Skype から別に移動 (たとえば、実行中にアップグレード) する場合は、Skype の部屋のシステム アカウントのプールに移動するのには次のコマンドを使用します。 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>ビジネス サービスの Skype の Skype ルームのシステム アカウントを無効にします。

Skype ルーム システムの既存のアカウント Skype からビジネス ・ サービス、Skype ビジネス サーバー プールの上を無効にする場合は、アカウントを無効にする次のコマンドを使用します。 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>オプション: Active Directory で Skype ルームのシステム管理者グループを作成します。

各 Skype ルーム システム クライアントがドメインに参加するは、PC の Skype ルーム システム ・ アプライアンスのローカル管理者権限を持つドメイン ユーザーによって完全に管理できます。 したがって、Active Directory 内に専任の管理者のグループを作成して新しい Skype ルーム システム マシンのセットの中このグループの管理者権限を与えます。
  

