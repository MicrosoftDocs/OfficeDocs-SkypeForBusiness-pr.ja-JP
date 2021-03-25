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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113203"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Exchange ユニファイド メッセージングとホスト型ボイス メールを管理する

[] 一連のコマンドレットを使用して、Exchange ユニファイド メッセージング、Skype for Business Online のホスト型ボイスメールを管理できます。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Exchange ユニファイド メッセージングとホスト型ボイス メールの管理

次のコマンドレットを使用して、Exchange ユニファイド メッセージング (UM) とホスト型ボイスメール のポリシーを管理できます。
  

| **コマンドレット**                                                                                                                                                                                                                                                                                                                        | **説明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Exchange UM がホストされるサービスである場合、このコマンドレットは自動応答およびサブスクライバー アクセスで使用する連絡先オブジェクトを作成、管理します。  <br/><br/> Skype for Business Online では、Exchange UM と連係して、自動応答やサブスクライバー アクセスといった音声関連の機能が提供されています。自動応答は、着信に自動的に応答したり、適切な人物に通話を経由する機能です。サブスクライバー アクセスを使用すると、ユーザーは Exchange UM にアクセスして、電子メール、音声メッセージ、連絡先、予定表情報を取得できます。<br/><br/> Exchange UM がホストされたサービスとして提供されている場合は、Microsoft PowerShell を使用して、自動応答やサブスクライバー アクセスのサービスで使用する連絡先オブジェクトを作成する必要があります。連絡先オブジェクトは **CsExUmContact** コマンドレットを使用して作成、管理します。<br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | 組織で使用するホスト型ボイスメールのポリシーを管理します。ホスト型ボイスメールのポリシーでは、不在着信を Exchange UM サービスに経由する方法を指定します。これらのポリシーは、Exchange UM にホストされるボイスメールが有効化されたユーザーにのみ影響します。    <br/><br/> ホスト型ボイスメールが有効化されているかどうかを確認するには、PowerShell プロンプトで次のようなコマンドを実行します。  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>関連項目
[Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
