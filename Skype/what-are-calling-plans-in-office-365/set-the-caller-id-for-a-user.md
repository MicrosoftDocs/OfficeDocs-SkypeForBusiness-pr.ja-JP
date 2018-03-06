---
title: "ユーザーに発信者番号を設定する"
ms.author: tonysmit
author: tonysmit
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
description: "Office 365 の電話システムは、ユーザーの割り当てられた電話番号である既定の発信者番号を提供します。ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。組織での発信者番号の使用方法の詳細については、組織内での発信者番号の使用方法をご覧ください。"
---

# ユーザーに発信者番号を設定する

Office 365 の電話システムは、ユーザーの割り当てられた電話番号である既定の発信者番号を提供します。ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
> [!TIP]
> Skype for Business Online で、着信通話を遮断することは現時点ではできません。 
  
次の設定を変更できます。
  
> [!NOTE]
> これは、Lync または Skype for Business Server を使用するオンプレミスの組織向け **ではありません**
  
- **発信する発信者番号を変更する**: ユーザーの発信者番号は、既定で電話番号になっていますが、別の電話番号に置き換えることができます。たとえば、ユーザーの発信者番号を個人電話番号から会社の代表電話番号に変更したり、ユーザーの通話回線番号を個人電話番号から法務部の代表電話番号に変更したりできます。発信者番号はどのオンライン **サービス** 番号 (有料電話番号または無料電話番号) にでも変更することができます。
    
    > [!NOTE]
    >  _Service_ パラメーターを使用する場合は、有効のサービス番号を指定する必要があります。
  
- **発信する発信者番号を禁止する**: ユーザーの発信する PSTN 通話に発信者番号が送信されるのを禁止することができます。このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。
    
- **着信する発信者番号を禁止する**: あらゆる着信 PSTN 通話でユーザーが発信者番号を受信できないようにします。
    
> [!IMPORTANT]
> 緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。 
  
既定では、これらのすべての発信者番号設定が **オフ** になっています。このため、Skype for Business Online のユーザーが PSTN 電話に通話を発信すると、そのユーザーの電話番号は相手に表示されることになります。
  
これらの設定と使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
## 発信者番号ポリシー設定を設定する

> [!NOTE]
> Skype for Business Online のすべての発信者番号設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
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
    
### 組織内のすべての発信者番号のポリシー設定を表示する

- 組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。
    
  - 
  ```
  Get-CsCallingLineIdentity |fl
  ```

    [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx) のその他の例と詳細について確認してください。
    
### 組織の新しい発信者番号ポリシーを作成します

- 発信者番号を匿名に設定する発信者番号ポリシーを新たに作成するには、次を実行します。
    
  - 
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

    [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx) のその他の例と詳細について確認してください。
    
- Amos Marble に作成した新しいポリシーを適用するには、次を実行します。
    
  - 
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```

    詳細については、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) コマンドレットをご覧ください。
    
ポリシーを作成済みの場合は、[Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) を使用して設定をユーザーに適用します。
  
### 着信する発信者番号を禁止するように設定する

- 着信する発信者番号を禁止するには、次を実行します。
    
  - 
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```

    [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) のその他の例と詳細について確認してください。
    
- 作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。
    
  - 
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```

    詳細については、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) コマンドレットをご覧ください。
    
### 発信者番号ポリシーを削除する

組織からポリシーを削除するには、次を実行します。
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```

ユーザーからポリシーを削除するには、次を実行します。
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```

## Windows PowerShell の詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 関連トピック

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)
  
[音声会議無料ダイヤルアウト期間](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  

