---
title: Skype Room System と Skype for Business フェデレーション パートナー
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
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820807"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System と Skype for Business フェデレーション パートナー
 
このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System と Skype for Business フェデレーション パートナー

Skype Room System は、予定表の会議出席依頼の [Skype for Business 会議に参加する] リンクに依存します。 通常、参加リンクは会議出席依頼の本文に表示されます。 ただし、Skype Room System は、このリンクがメッセージの MAPI プロパティに存在する必要があります。 この会議出席依頼がリモート組織 (Skype for Business フェデレーション パートナー) に送信される場合、既定では、リモート組織の Skype Room System は予定表に会議参加リンクを表示します。 実際、リモート組織の Outlook ユーザーは、予定表アイテムを右クリックするか、会議のアラーム内から Skype for Business 会議に参加できません。 会議の招待を開き、メッセージの本文で [Skype for Business 会議に参加] をクリックする必要があります。 
  
この制限の理由は、Outlook と Microsoft Exchange がインターネットを通してメッセージを送信する情報をパッケージ化するために特別な方法を使用しなだからです。 トランスポート ニュートラル カプセル化形式 (TNEF) と呼ばれるこのメソッドは、Exchange 組織から外部に送信されるメッセージに対して既定で無効になっています。 会議参加リンクをリモートの Skype Room System に表示するには、次のコマンドを使用して送信組織が TNEF を有効にする必要があります。
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

リモート組織で TNEF が有効になると、インターネットを通して組織に送信されるメッセージは、TNEF 形式の添付ファイルとして送信されます。 TNEF を有効にすると、Skype for Business の会議出席依頼が Skype for Business フェデレーション パートナーに送信された場合、Skype Room System は Skype for Business 会議に参加し、リモート ユーザーは Skype for Business 会議に参加できます。 
