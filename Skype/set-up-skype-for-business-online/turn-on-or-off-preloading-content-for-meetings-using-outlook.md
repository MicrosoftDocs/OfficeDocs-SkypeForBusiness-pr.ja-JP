---
title: "Outlook 会議で使用するコンテンツ プリロードの有効化と無効化"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
description: "See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. "
---

# Outlook 会議で使用するコンテンツ プリロードの有効化と無効化

Outlook 会議の出席依頼に添付されたファイルなどのコンテンツをプリロードして Skype for Business Online 会議で使用することができます。この機能は有効/無効を切り替えることができます。この機能は、Skype for Business Online を使用するすべての組織で有効にされています。「[Skype for Business 会議で使用する添付ファイルのプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)」を参照してください。
  
> [!NOTE]
> 現在、Skype for Business Online には  _MaxContentStorageMB_ と _MaxUploadFileMB_ の値を設定またはオンラインで表示するコマンドレットはありません。これは、オンプレミス環境でのみ使用できます。添付されたコンテンツが _MaxUploadFileSizeMB_ を超える場合や、 _MaxContentStorageMB_ の制限に達した場合、コンテンツのアップロードはできません。> 
  
## 使用するには、次のようにします。

### 

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
  
1. バージョン 3.0 以降を実行していることを確認するには [ **スタート**] メニューから [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
  
### 

 **Windows PowerShell セッションを開始する**
  
1. [ **スタート**] メニューで [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」または「[Windows PowerShell を使用した Lync Online への接続](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。
  
## 機能の有効化と無効化

Outlook 会議の出席依頼に添付されたコンテンツを Skype for Business Online 会議で使用するためのプリロード機能は、既定で有効にされています。ただし、場合によっては組織でユーザーがコンテンツをプリロードしないようにする必要があります。
  
> [!IMPORTANT]
> この設定の有効化/無効化は組織全体でのみ行うことができ、単一ユーザーで有効/無効にすることはできません。 
  
 **無効にするには、Windows PowerShell を開いて、次を行います。**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **再び有効にするには、Windows PowerShell を開いて、次を行います。**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## Windows PowerShell の詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    

