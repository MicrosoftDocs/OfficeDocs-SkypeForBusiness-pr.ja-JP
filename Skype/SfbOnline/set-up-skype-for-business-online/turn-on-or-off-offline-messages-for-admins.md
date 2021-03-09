---
title: オフライン メッセージの有効化と無効化 (管理者向け)
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568757"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>オフライン メッセージの有効化と無効化 (管理者向け)

[] サインインしていない連絡先にも Skype for Business で IM を送信できるようになりました。これにより、連絡しようとしていることを相手に知らせることができます。相手がオンラインでなくても、メッセージを送ることができます。

オフライン メッセージでは、次のことに注意する必要があります。

- オフライン メッセージはユーザーの受信箱にアーカイブされません。

- オフライン メッセージがユーザーの受信箱に送信され、ユーザーが Skype for Business にログインすると、受信が通知されます。

- メッセージ受信者のステータスが [ **応答不可**] または [ **プレゼンテーション中**] に設定されている場合は、受信者の Skype for Business クライアントから不在着信メッセージが送られます。

詳細については、「[Skype for Business でオフライン メッセージを使う](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)」をご覧ください。

## <a name="to-get-you-started"></a>使用するには、次のようにします。

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウですべての[Office 365](https://technet.microsoft.com/library/dn568015.aspx)サービスに接続する」または「Windows PowerShell[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)用にコンピューターをセットアップする」を参照してください。

## <a name="turning-on-or-off-offline-im"></a>オフライン IM の有効化と無効化

> [!NOTE]
> オフライン メッセージは、最新バージョンのクイック実行 Skype for Business クライアントで **のみ** 使用できます。旧バージョンのクイック実行 Skype for Business を使用している場合や *.msi ファイルを使用して Skype for Business クライアントをインストールした場合は、使用できません。

組織のユーザーのオフラインメッセージの送信を有効または無効にするには、[ _EnableIMAutoArchiving_] を [ `True`] または [ `False`] に設定します。 既定では、この設定は `True` .

この設定をオフにするには、 **Set-CsClientPolicy** コマンドレットを使用して、実行します。

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

1 人のユーザーのオフラインメッセージの送信を有効または無効にするには、[ _EnableIMAutoArchiving_] を [ `True`] または [ `False`] に設定します。 既定ではこれは  `True` に設定されています。 既存のポリシーを使用するか、次の例のようなポリシーを作成できます。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
