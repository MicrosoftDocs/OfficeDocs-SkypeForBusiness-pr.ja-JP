---
title: "無効を切り替える Skype for Business クライアントのフィードバックのレポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Skype for Business ユーザーがユーザーが問題を報告経験について Microsoft に直接フィードバックを提供できるようにする組み込み Skype for Business アプリのフィードバック ツールを使用することができます。"
ms.openlocfilehash: c60057e2b303fb9265560754fb4bb2643685ac5c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>無効を切り替える Skype for Business クライアントのフィードバックのレポート

Skype for Business ユーザーがユーザーが問題を報告経験について Microsoft に直接フィードバックを提供できるようにする組み込み Skype for Business アプリのフィードバック ツールを使用することができます。 
  
![Skype for Business クライアントのレポートにはします。](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
このツールでは、ユーザーは、Microsoft よりを調査して可能性がある問題のトラブルシューティングのために、デバイス上のアプリケーションからログをコピーできます。 
  
![Skype for Business クライアントのレポートにはします。](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
ユーザーが自分のフィードバックの一部として、デバイスのスクリーン ショットを含めることができます_EnableOnlineFeedbackScreenshot_設定を使用することもできます。
  
![Skype for Business クライアントのフォームをレポートにはします。](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> アプリのフィードバック ツールによって収集されたログを保存する問題の中には、米国内で最大 90 日間の調査にします。このため、有効にしないでくださいこのフィードバック ツール、組織のデータ保護ポリシーを次に違反している場合。 
  
## <a name="verify-and-start-windows-powershell"></a>確認し、Windows PowerShell を起動する.

- **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
    
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
    
- **Windows PowerShell セッションを開始します。**
    
1. **[スタート] メニュー**から > **Windows PowerShell**します。
    
2. **Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```
詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>組織内のすべてのユーザーに関するレポートのクライアント アプリケーション フィードバックを有効にします。

フィードバックは、組織のユーザーの報告を有効にし、デバイスのスクリーン ショットを送信できるように、次のコマンドを実行します。
> 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細を知りたいとしていますか。
- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。](let-skype-for-business-users-add-skype-contacts.md)