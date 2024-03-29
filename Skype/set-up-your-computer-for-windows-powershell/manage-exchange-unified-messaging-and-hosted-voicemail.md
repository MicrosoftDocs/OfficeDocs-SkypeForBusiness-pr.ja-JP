---
title: "Exchange ユニファイド メッセージングと Skype for Business Online のホスト型のボイスメールの管理"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# Exchange ユニファイド メッセージングと Skype for Business Online のホスト型のボイスメールの管理

一連のコマンドレットを使用して、Exchange ユニファイド メッセージング、Skype for Business Online のホスト型ボイスメールを管理できます。
  
## Exchange ユニファイド メッセージングとホスト型ボイス メールの管理

次のコマンドレットを使用して、Exchange ユニファイド メッセージング (UM) とホスト型ボイスメール のポリシーを管理できます。
  
|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Exchange UM がホストされるサービスである場合、このコマンドレットは自動応答およびサブスクライバー アクセスで使用する連絡先オブジェクトを作成、管理します。  <br/> Skype for Business Online では、Exchange UM と連係して、自動応答やサブスクライバー アクセスといった音声関連の機能が提供されています。自動応答は、着信に自動的に応答したり、適切な人物に通話を経由する機能です。サブスクライバー アクセスを使用すると、ユーザーは Exchange UM にアクセスして、電子メール、音声メッセージ、連絡先、予定表情報を取得できます。  <br/> Exchange UM がホストされたサービスとして提供されている場合は、Microsoft PowerShell を使用して、自動応答やサブスクライバー アクセスのサービスで使用する連絡先オブジェクトを作成する必要があります。連絡先オブジェクトは **CsExUmContact** コマンドレットを使用して作成、管理します。 <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |組織で使用するホスト型ボイスメールのポリシーを管理します。ホスト型ボイスメールのポリシーでは、不在着信を Exchange UM サービスに経由する方法を指定します。これらのポリシーは、Exchange UM にホストされるボイスメールが有効化されたユーザーにのみ影響します。  <br/> ホスト型ボイスメールが有効化されているかどうかを確認するには、PowerShell プロンプトで次のようなコマンドを実行します。  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   

