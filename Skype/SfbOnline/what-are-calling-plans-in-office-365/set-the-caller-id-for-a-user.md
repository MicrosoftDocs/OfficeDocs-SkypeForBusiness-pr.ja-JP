---
title: "ユーザーの発信者番号を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Office 365 で電話システムでは、ユーザーの割り当てられている電話番号を既定の発信者番号を提供します。変更するかユーザーの (呼び出しの行 ID とも呼ばれます) の発信者番号をブロックすることができます。発信者の使い方、組織内では、組織内の発信者番号を使用する方法の詳細を学びます。"
ms.openlocfilehash: 3ac690bd331e050abd18be8bc559f9ea555c815a
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-the-caller-id-for-a-user"></a>ユーザーの発信者番号を設定します。
Office 365 で電話システムでは、ユーザーの割り当てられている電話番号を既定の発信者番号を提供します。変更するかユーザーの (呼び出しの行 ID とも呼ばれます) の発信者番号をブロックすることができます。[発信者の使い方組織内](how-can-caller-id-be-used-in-your-organization.md)を移動して、組織内の発信者番号を使用する方法を学びます。
  
> [!TIP]
> For Business Online Skype で現在の着信をブロックすることはできません。 
  
変更できる設定があります。
  
> [!NOTE]
> これ**は**Business Server の Lync または Skype の社内組織の場合です。
  
- **変更の送信の発信者番号**別の電話番号を使って、電話番号には、ユーザーの発信者番号を置き換えることができます。たとえば、業務用の電話番号からメインの電話番号、ユーザーの発信者番号を変更または法的部門のメインの電話番号、電話番号からユーザーの呼び出し行 ID を変更する可能性があります。呼び出す番号を変更すると、オンライン**サービス**の数値を指定することができます (有料またはフリー ダイヤル)。
    
    > [!NOTE]
    > _サービス_のパラメーターを使用する場合は、有効なサービス数を指定する必要があります。
  
- **ブロックの外部の発信者番号**PSTN 通話を発信するユーザーの送信されない送信の発信者番号をブロックすることができます。これから呼び出される人の電話に表示されている電話番号がブロックされます。
    
- **ブロックの着信の発信者番号**発信者番号を受信しない、PSTN 通話を受信したユーザーをブロックすることができます。
    
> [!IMPORTANT]
> 緊急の通話には、常にユーザーの電話番号 (発信者) が送信されます。 
  
既定では、これらの呼び出し元 ID 設定がすべて**オフになっています**。つまりと、そのユーザーは、PSTN の電話番号に通話を Skype for Business Online のユーザーの電話番号を表示することができます。
  
これらの設定と使用する方法の詳細については、[発信者の使い方組織内](how-can-caller-id-be-used-in-your-organization.md)を移動します。
  
## <a name="set-your-caller-id-policy-settings"></a>ID ポリシーの呼び出し元の設定します。

> [!NOTE]
> Skype for Business Online 発信者設定のすべての Windows PowerShell と**使用できない** **Skype for Business 管理センター**を使用する必要があります。 
  
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

詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>発信者 ID ポリシーの設定を組織内のすべてを参照してください。

- 組織では、すべての呼び出し元の ID ポリシーの設定を表示、次のコマンドを実行します。

  ```
  Get-CsCallingLineIdentity |fl
  ```
[Get CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)の他の例と詳細を参照してください。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>組織用の新しい発信者 ID ポリシーを作成します。

- 匿名の発信者番号を設定する新しい発信者 ID ポリシーを作成するには、次のコマンドを実行します。
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

  [新規 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)の他の例と詳細を参照してください。
    
- Amos 大理石に作成した新しいポリシーを適用するには、次のコマンドを実行します。
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  [許可を付与する CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットの詳細を参照してください。
    
既にポリシーを作成している場合は、[セット CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットを使用します。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>着信、発信者がブロックされているように設定します。

- 着信の発信者番号をブロックするには、次のコマンドを実行します。
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  [セット CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)その他の例と詳細を参照してください。
    
- 作成したポリシーの設定を適用するには、組織内のユーザーに、次のように実行します。
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    [許可を付与する CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットの詳細を参照してください。
    
### <a name="remove-a-caller-id-policy"></a>発信者 ID ポリシーを削除します。

組織内のポリシーを削除するには、次のコマンドを実行します。
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
ポリシーを削除するユーザーから、次のコマンドを実行します。
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
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
[電話番号のよく寄せられる質問を転送します。](transferring-phone-numbers-common-questions.md)

[さまざまなプランの呼び出し用の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理します。](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急の呼び出し元の条項および条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急発信免責事項のラベル](https://go.microsoft.com/fwlink/?LinkID=692099)
  

