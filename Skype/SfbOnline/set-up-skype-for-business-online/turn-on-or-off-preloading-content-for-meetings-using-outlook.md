---
title: "オンまたはオフに Outlook を使用して会議のプリロードされたコンテンツを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: "プリロードされたコンテンツを切り替える skype for Business の会議、Outlook の会議出席依頼にファイルまたは添付ファイルを使用する方法を参照してください。 "
ms.openlocfilehash: 33f412388d08d37154c1700a61908e310e9375d3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>オンまたはオフに Outlook を使用して会議のプリロードされたコンテンツを有効にします。

コンテンツ、ファイル、または添付ファイルを Outlook 会議出席依頼に Skype for Business Online の会議に接続されているユーザーにプリロードすることができます、オンまたはオフにします。これは、ために、Skype for Business Online を使用しているすべての組織の既定でなっています。表示[する Skype for Business 会議の添付ファイルをプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)する方法。
  
> [!NOTE]
> 現時点ではありませんコマンドレットの設定]、または_MaxContentStorageMB_と_MaxUploadFileMB_のオンラインの値を表示する Skype for Business Online で利用できます。内部設置型の展開についてはのみです。確認することが重要_MaxContentStorageMB_制限に達した場合や接続されているコンテンツが_MaxUploadFileSizeMB_を超えると、会議にコンテンツをアップロードしません。
  
## <a name="to-get-you-started"></a>使い始めるときに

### 

 **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
  
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
  
### 

 **Windows PowerShell セッションを開始します。**
  
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
  
## <a name="turning-it-on-or-off"></a>オンまたはオフ

Outlook 会議の招待状に Skype for Business Online の会議に接続されているコンテンツを事前にできることが有効で、既定では、会議の内容をプリロードから組織のユーザーを防止する必要があります。
  
> [!IMPORTANT]
> この設定だけができますオンまたはオフに組織の全体用にします。1 人のユーザーの機能のオンとオフを有効にすることはできません。 
  
 **オフにするにはを Windows PowerShell を開き、次の操作します。**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **操作に戻り、Windows PowerShell を開いていることを有効にして、次の操作を行う場合**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
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
