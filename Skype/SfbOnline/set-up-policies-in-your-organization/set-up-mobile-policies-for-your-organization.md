---
title: 組織のモバイル ポリシーをセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。
ms.openlocfilehash: 21d1b19a72686d618bf8fca484bf828e62ee3a37
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861529"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>組織のモバイル ポリシーをセットアップする

[] モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。
  
モバイル機能ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsMobilityPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## <a name="set-your-mobile-policies"></a>モバイル機能ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのモバイル機能ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>ユーザーに対してビデオ使用時に WiFi 接続を要求する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  [新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  [許可 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。
    
  ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) を使用して設定をユーザーに適用します。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>ユーザーが Skype for Business アプリを使用できないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  [新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  [許可 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。
    
  ポリシーを既に作成した場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して既存のポリシーに変更を加えるし、[許可 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用して設定をユーザーに適用します。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>ユーザーがモバイル デバイスを使用してボイス オーバー IP 通話を行えないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  [新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  [許可 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。
    
ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) を使用して設定をユーザーに適用します。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ブロック ポイント ツー ポイントのファイルの転送](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーを設定します](set-up-conferencing-policies-for-your-organization.md)

  
 