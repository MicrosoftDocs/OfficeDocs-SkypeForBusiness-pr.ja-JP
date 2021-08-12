---
title: SkypeRoom System と Skype for Businessフェデレーション パートナー
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
description: このトピックを参照して、フェデレーション パートナー向Skype Room System をSkype for Businessしてください。
ms.openlocfilehash: ba31d945425c2f5e32bc09e6b97c6204e492f414b5ca6b2e5ceaf3e65d0de3be
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294914"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>SkypeRoom System と Skype for Businessフェデレーション パートナー
 
このトピックを参照して、フェデレーション パートナー向Skype Room System をSkype for Businessしてください。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>SkypeRoom System と Skype for Businessフェデレーション パートナー

Skype会議室システムは、予定表の会議出席依頼Skype for Business [会議に参加する] リンクに依存します。 通常、参加リンクは会議出席依頼の本文に表示されます。 ただし、Skypeシステムは、メッセージの MAPI プロパティに存在するこのリンクに依存します。 この会議出席依頼がリモート組織 (Skype for Business フェデレーション パートナー) に送信される場合、既定では、リモート組織の Skype 会議室システムは会議参加リンクを予定表に表示されません。 実際、リモート組織Outlookユーザーは、予定表アイテムを右クリックするか、会議のリマインダー内から Skype for Business 会議に参加できません。 会議出席招待を開き、メッセージの本文Skype for Business [会議に参加する] をクリックする必要があります。 
  
この制限の理由は、Outlook Microsoft Exchange、インターネットを通してメッセージを送信する情報をパッケージ化する特別な方法を使用しないという理由です。 トランスポート ニュートラル カプセル化形式 (TNEF) と呼ばれるこのメソッドは、組織から外部に送信されるメッセージに対して既定Exchangeされます。 会議参加リンクを会議室システムのリモート Skype表示するには、次のコマンドを使用して送信組織が TNEF を有効にする必要があります。
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

リモート組織で TNEF が有効になると、インターネットを通して組織に送信されたメッセージは、TNEF 形式の添付ファイルとして送信されます。 TNEF を有効にすると、Skype for Business 会議出席依頼が Skype for Business フェデレーション パートナーに送信された場合、Skype 会議室システムは Skype for Business 会議に参加し、リモート ユーザーは Skype for Business 会議に参加できます。 
