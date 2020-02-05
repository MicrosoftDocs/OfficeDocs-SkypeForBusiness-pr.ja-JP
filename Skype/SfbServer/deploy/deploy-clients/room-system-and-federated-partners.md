---
title: Skype Room System および Skype for Business のフェデレーション パートナー
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
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
ms.openlocfilehash: d5ee83857aa439791e2a31ef201e0f365dbb8408
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768720"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System および Skype for Business のフェデレーション パートナー
 
このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System および Skype for Business のフェデレーション パートナー

Skype Room System は、予定表の会議出席依頼の [Skype for Business 会議への参加] リンクに依存しています。 通常、この参加リンクは会議出席依頼の本文に用意されています。 ただし、Skype Room システムは、このリンクに依存して、メッセージの MAPI プロパティに表示されます。 この会議出席依頼がリモート組織 (Skype for Business フェデレーションパートナー) に送信されると、既定では、リモート組織の Skype Room System には予定表の [会議参加] リンクが表示されません。 実際には、リモート組織のすべての Outlook ユーザーは、予定表アイテムを右クリックするか、会議のアラーム内から、Skype for Business 会議に参加することはできません。 会議出席依頼を開き、メッセージの本文で [Skype for Business 会議に参加する] をクリックする必要があります。 
  
この制約事項は、Outlook と Microsoft Exchange がインターネット経由でメッセージを送信するためのある特別な情報パッケージ化手法を使用していないことに起因しています。 Transport Neutral Encapsulation Format (TNEF) と呼ばれるこの手法は、Exchange 組織外から送信されたメッセージに対して、既定で無効になっています。 会議参加リンクがリモートの Skype Room システムに表示されるようにするには、次のコマンドを使用して、送信側の組織が TNEF を有効にする必要があります。
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

リモート組織に対して TNEF を有効にすると、その組織宛てにインターネット経由で送信されるあらゆるメッセージが、TNEF 形式の添付ファイルとして送信されます。 TNEF を有効にすると、skype for business のフェデレーションパートナーに Skype for Business 会議出席依頼が送信されると、skype Room System は skype for business 会議に参加することができ、リモートユーザーは Skype for Business 会議に参加できるようになります。 
