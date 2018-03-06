---
title: "組織の電話会議ポリシーをセットアップする"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
description: "電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。"
---

# 組織の電話会議ポリシーをセットアップする

電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。
  
電話会議および電話会議の設定を制御できる状態を維持することが重要です。場合によって、セキュリティに関する問題があるかもしれません。既定では、未認証のユーザーを含むあらゆるユーザーが会議に参加でき、その会議中に配布されたスライドや資料を保存することができます。さらに、時には法的な問題が発生することもあります。たとえば、既定では会議の参加者は共有コンテンツに注釈を付けることができますが、それらの注釈は会議がアーカイブされるときに保存されません。所属する組織ですべての電子的な通信の記録を保持する必要がある場合は、注釈を無効にする方が良い可能性があります。
  
Skype for Business Online では、電話会議は電話会議ポリシーを使用して管理されます。電話会議ポリシーにより、電話会議に IP オーディオまたはビデオを含めることができるかということから、会議に出席できるユーザーの最大数についてまで、あらゆる点を含む電話会議で使用できる機能が決まります。電話会議ポリシーは全体的な範囲またはユーザーごとの範囲で構成できます。これにより、管理者は、どの機能をどのユーザーが利用できるようにするかを決めるときに、最大の柔軟性を発揮できます。
  
ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsConferencingPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## 電話会議ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべての電話会議ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. バージョン 3.0 以降を実行していることを確認するには [ **スタート**] メニューから [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
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
    
### 会議中のファイル転送およびデスクトップ共有を禁止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```

    詳細については、[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) コマンドレットをご覧ください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与します。次を実行します。
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```

    詳細については、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットをご覧ください。
    
ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。
  
### 電話会議のレコーディングを禁止し、匿名ユーザーの会議参加者を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```

    詳細については、[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) コマンドレットをご覧ください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
    
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```

    詳細については、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットをご覧ください。
    
ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。
  
### 匿名ユーザーの参加者による会議のレコーディングと、追加ユーザーによる会議の内容の保存を禁止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```

    詳細については、[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) コマンドレットをご覧ください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

    詳細については、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットをご覧ください。
    
ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。
  
## Windows PowerShell の詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    

