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
ms.openlocfilehash: 4af24f66aa82bbd0f0099e062981157b08c639db
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164096"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>オフライン メッセージの有効化と無効化 (管理者向け)

[] サインインしていない連絡先にも Skype for Business で IM を送信できるようになりました。これにより、連絡しようとしていることを相手に知らせることができます。相手がオンラインでなくても、メッセージを送ることができます。

オフライン メッセージでは、次のことに注意する必要があります。

- オフライン メッセージはユーザーの受信箱にアーカイブされません。

- オフライン メッセージがユーザーの受信箱に送信され、ユーザーが Skype for Business にログインすると、受信が通知されます。

- メッセージ受信者のステータスが [ **応答不可**] または [ **プレゼンテーション中**] に設定されている場合は、受信者の Skype for Business クライアントから不在着信メッセージが送られます。

詳細については、「[Skype for Business でオフライン メッセージを使う](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)」をご覧ください。

## <a name="to-get-you-started"></a>使用するには、次のようにします。

## #

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**

1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。

2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。

3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。

4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。

詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。

## #

 **Windows PowerShell セッションを開始する**

1. From the **Start Menu** > **Windows PowerShell**.

2. **Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。

    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。

## <a name="turning-on-or-off-offline-im"></a>オフライン IM の有効化と無効化

> [!NOTE]
> オフライン メッセージは、最新バージョンのクイック実行 Skype for Business クライアントで **のみ** 使用できます。旧バージョンのクイック実行 Skype for Business を使用している場合や *.msi ファイルを使用して Skype for Business クライアントをインストールした場合は、使用できません。

組織のユーザーのオフラインメッセージの送信を有効または無効にするには、[ _EnableIMAutoArchiving_] を [ `True`] または [ `False`] に設定します。 既定では、これはに`True`設定されます。

この設定をオフにするには、 **Set-CsClientPolicy** コマンドレットを使用して、実行します。

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

1 人のユーザーのオフラインメッセージの送信を有効または無効にするには、[ _EnableIMAutoArchiving_] を [ `True`] または [ `False`] に設定します。 既定ではこれは  `True` に設定されています。 既存のポリシーを使用することも、次の例のように作成することもできます。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。

  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)


