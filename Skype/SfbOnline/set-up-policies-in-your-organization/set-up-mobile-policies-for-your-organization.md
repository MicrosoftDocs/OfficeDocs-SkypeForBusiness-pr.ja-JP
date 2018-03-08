---
title: "組織用のモバイルのポリシーを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: "ビジネスのアプリを行い、勤務先の電話番号を使用して、携帯電話番号の連ではなく、携帯電話で通話を受信できるようにする機能などのモバイル デバイスでの Skype を使用するのには、Skype for Business Online ユーザーの接続を設定できます。mber します。移動ポリシーは、Wi-fi 接続されたとき、または通話の発着信を要求するも使用できます。"
ms.openlocfilehash: 904da369a4218b0b41112c97a1fed9de03c47c3b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-mobile-policies-for-your-organization"></a>組織用のモバイルのポリシーを設定します。

ビジネスのアプリを行い、勤務先の電話番号を使用して、携帯電話番号の連ではなく、携帯電話で通話を受信できるようにする機能などのモバイル デバイスでの Skype を使用するのには、Skype for Business Online ユーザーの接続を設定できます。mber します。移動ポリシーは、Wi-fi 接続されたとき、または通話の発着信を要求するも使用できます。
  
ポリシーを作成すると、時にモバイル ポリシーの設定を構成することができますか、既存のポリシーの設定を変更する**設定 CsMobilityPolicy**コマンドレットを使用することができます。
  
## <a name="set-your-mobile-policies"></a>モバイルのポリシーを設定します。

> [!NOTE]
> すべてのモバイル ポリシーの設定で Skype for Business Online の Windows PowerShell と**使用できない** **Skype for Business 管理センター**を使用する必要があります。 
  
### <a name="verify-and-start-windows-powershell"></a>確認し、Windows PowerShell を起動する.

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

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>ユーザーのビデオの WiFi 接続が必要

- これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  [新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。
    
- 組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  [許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。
    
  既にポリシーを作成している場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに設定を適用する[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用します。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>ユーザーが、Skype を for Business アプリを使用するを防ぐ

- これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  [新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。
    
- 作成した新しいポリシーを Amos 大理石に付与するには、次のように実行します。  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  [許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。
    
  既にポリシーを作成している場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに設定を適用する[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用します。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>ユーザーがモバイル デバイスを使って IP 電話で音声を作成するを防ぐ

- これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  [新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。
    
- 組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  [許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。
    
既にポリシーを作成している場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに設定を適用する[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用します。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細を知りたいとしていますか。

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[ユーザー設定の外部アクセス ポリシーを作成します。](create-custom-external-access-policies.md)

[ブロック ポイント間接ファイル転送](block-point-to-point-file-transfers.md)

[組織のクライアントのポリシーを設定します。](set-up-client-policies-for-your-organization.md)

[組織内の会議のポリシーを設定します。](set-up-conferencing-policies-for-your-organization.md)

