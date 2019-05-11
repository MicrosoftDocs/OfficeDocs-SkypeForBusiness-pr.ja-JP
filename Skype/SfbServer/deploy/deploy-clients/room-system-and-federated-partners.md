---
title: Skype Room System および Skype for Business のフェデレーション パートナー
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
ms.openlocfilehash: 30668641f2c43981485531722861647fdeffc710
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895020"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System および Skype for Business のフェデレーション パートナー
 
このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System および Skype for Business のフェデレーション パートナー

Skype ルーム システムは、予定表の会議出席依頼に会議のリンクの参加の Skype に依存しています。 通常、この参加リンクは会議出席依頼の本文に用意されています。 ただし、Skype の部屋のシステムは、メッセージの MAPI プロパティには、このリンクによって異なります。 この会議を要求するときに送信されますリモート組織 (連合のビジネス パートナーは、Skype) を既定では、リモート組織の Skype ルーム システムは会議の参加を予定表のリンクを表示しません。 実際には、リモート組織内のすべての Outlook ユーザーことはできませんアイテムまたは予定表の右クリックでのビジネス会議のための Skype に参加する会議のアラームにします。 会議出席依頼を開き、Skype の参加をクリックして、メッセージの本文に会議のする必要があります。 
  
この制約事項は、Outlook と Microsoft Exchange がインターネット経由でメッセージを送信するためのある特別な情報パッケージ化手法を使用していないことに起因しています。 Transport Neutral Encapsulation Format (TNEF) と呼ばれるこの手法は、Exchange 組織外から送信されたメッセージに対して、既定で無効になっています。 ミーティングの参加のリンクに表示されるリモート Skype ルームのシステムでは、送信元の組織は、次のコマンドを使用して、TNEF を有効にする必要があります。
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

リモート組織に対して TNEF を有効にすると、その組織宛てにインターネット経由で送信されるあらゆるメッセージが、TNEF 形式の添付ファイルとして送信されます。 TNEF を有効にすると、Skype のビジネス会議出席依頼に送信されます、フェデレーション パートナーのビジネスの Skype Skype ルームのシステムはビジネスの会議に参加 Skype をレンダリングすることになり、リモート ユーザーは Skype をビジネス ・ ミーティングに参加することになります。 
