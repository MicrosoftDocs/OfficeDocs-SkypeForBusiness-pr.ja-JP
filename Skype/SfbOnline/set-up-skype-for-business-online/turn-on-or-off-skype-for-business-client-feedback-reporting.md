---
title: Skype for Business クライアントのフィードバック レポートをオンまたはオフにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
- Setup
description: ユーザーの問題を報告し、経験についてマイクロソフトに直接フィードバックを提供できるようにするビジネス アプリケーションからのフィードバックのツールの組み込みの Skype を使用するビジネス ユーザー向けに、Skype を有効にできます。
ms.openlocfilehash: 6d8f5c7e7c333e447b4238e47dab1fc7ad394816
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850101"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Skype for Business クライアントのフィードバック レポートをオンまたはオフにする

オンライン ビジネス ユーザーがビジネス アプリケーションからのフィードバックのツールの組み込みの Skype を使用して、ユーザーが問題を報告し、経験についてマイクロソフトに直接フィードバックを提供できるようにするのには、Skype を有効にすることができます。 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
このツールを使用すると、ユーザーは Microsoft よりよく調査し、可能性がある問題のトラブルシューティングに役立つ、デバイス上のアプリケーションからのログをコピーできます。 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
デバイスのスクリーンショットをユーザーのフィードバックに含めるために  _EnableOnlineFeedbackScreenshot_ の設定を使用することもできます。
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> アプリケーションのフィードバック ツールによって収集されたログを保存する最大 90 日間の問題の中にアメリカ合衆国では調査されているのです。 これが所属する組織のデータ保護ポリシーに抵触する場合は、このフィードバック ツールを有効にしないでください。 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. [**スタート メニュー**]  >  [**Windows PowerShell**] を開きます。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```
Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Windows PowerShell を使用した Lync Online への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>組織のすべてのユーザーに対してクライアント アプリのフィードバック レポートをオンにする

組織内のユーザーのレポートのフィードバックを有効にし、デバイスのスクリーン ショットを送信することが、次のコマンドを実行します。
 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 
