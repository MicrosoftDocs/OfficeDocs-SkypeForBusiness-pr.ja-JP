---
title: Exchange ユニファイド メッセージングとホスト型ボイス メールを管理する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 02fda8c315807899983741f94c1f825de1ebf1a9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224400"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Exchange ユニファイド メッセージングとホスト型ボイス メールを管理する

[] 一連のコマンドレットを使用して、Exchange ユニファイド メッセージング、Skype for Business Online のホスト型ボイスメールを管理できます。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Exchange ユニファイド メッセージングとホスト型ボイス メールの管理

次のコマンドレットを使用して、Exchange ユニファイド メッセージング (UM) とホスト型ボイスメール のポリシーを管理できます。
  

| **コマンドレット**                                                                                                                                                                                                                                                                                                                        | **説明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [新しい-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[削除 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[セット CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Exchange UM がホストされるサービスである場合、このコマンドレットは自動応答およびサブスクライバー アクセスで使用する連絡先オブジェクトを作成、管理します。  <br/><br/> Skype for Business Online では、Exchange UM と連係して、自動応答やサブスクライバー アクセスといった音声関連の機能が提供されています。自動応答は、着信に自動的に応答したり、適切な人物に通話を経由する機能です。サブスクライバー アクセスを使用すると、ユーザーは Exchange UM にアクセスして、電子メール、音声メッセージ、連絡先、予定表情報を取得できます。<br/><br/> Exchange UM がホストされたサービスとして提供されている場合は、Microsoft PowerShell を使用して、自動応答やサブスクライバー アクセスのサービスで使用する連絡先オブジェクトを作成する必要があります。連絡先オブジェクトは **CsExUmContact** コマンドレットを使用して作成、管理します。<br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | 組織で使用するホスト型ボイスメールのポリシーを管理します。ホスト型ボイスメールのポリシーでは、不在着信を Exchange UM サービスに経由する方法を指定します。これらのポリシーは、Exchange UM にホストされるボイスメールが有効化されたユーザーにのみ影響します。    <br/><br/> ホスト型ボイスメールが有効化されているかどうかを確認するには、PowerShell プロンプトで次のようなコマンドを実行します。  <br/> \`Get-CsOnlineUser-"kenmyer@litwareinc.com"の Id                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>関連トピック
[Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します](set-up-your-computer-for-windows-powershell.md)

  
 
