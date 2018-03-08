---
title: "Exchange ユニファイド メッセージングを管理して、ボイス メールのホストされています。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "PowerShell を使用すると、for Business Online の自動応答、サブスクライバー アクセスと Skype でホストされているボイス メールなどの Exchange ユニファイド メッセージング機能を管理できます。"
ms.openlocfilehash: 98a7847f6d8ec5bebd1889aef57298bd36696918
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Exchange ユニファイド メッセージングを管理して、ボイス メールのホストされています。

Exchange ユニファイド メッセージングを管理できるして for Business Online のコマンドレットを使用して Skype でボイス メールをホストします。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Exchange ユニファイド メッセージングを管理して、ボイス メールのホストされています。

次のコマンドレットでは、Exchange ユニファイド メッセージング (UM) を管理するために使用して、ボイス メールのポリシーをホストされています。
  
|**コマンドレット**|**{Description}**|
|:-----|:-----|
|[Get CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [新しい-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[削除 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[設定 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |作成し、ホストされているサービスが Exchange UM とき、サービスの自動応答、サブスクライバー アクセスに使用される連絡先のオブジェクトを管理します。  <br/><br/> Skype for Business Online 機能 UM 自動応答、サブスクライバー アクセスなどのいくつかの音声機能を提供します。自動応答には、通話が自動的に応答して適切な宛先にルーティングするための方法が用意されています。サブスクライバー アクセスでは、UM Exchange に接続してメール、音声メッセージ、連絡先、および予定表の情報を取得することができます。<br/><br/> UM がホストされているサービスとして指定する場合、Microsoft PowerShell を使用して、自動応答とサブスクライバー アクセス サービスのために、連絡先のオブジェクトを作成する必要があります。これらのオブジェクトが作成され、 **CsExUmContact**コマンドレットを使用して管理します。<br/> |
|[Get CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[許可を付与する CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |組織内で使用されているボイス メールのホスト ポリシーを管理します。ボイス メールのホストのポリシーの指定方法不在時の着信は、UM サービスにルーティングします。これらのポリシーでは、UM ホストされているボイス メールが有効になっているユーザーだけに影響します。  <br/><br/> ボイス メールのホストのユーザーが有効になっているかどうかを確認するには、PowerShell のプロンプトで、次のようなコマンドを実行します。  <br/> ' Get CsOnlineUser-"kenmyer@litwareinc.com"の Id | [オブジェクトの HostedVoiceMail'|
   

## <a name="related-topics"></a>関連トピック
[Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。](set-up-your-computer-for-windows-powershell.md)