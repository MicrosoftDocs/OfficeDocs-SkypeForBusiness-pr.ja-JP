---
title: Windows PowerShell 3.0 をダウンロードしてインストールします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: e3f1ca14b5c9e134ee5186b6c441fc948d1ef65b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="download-and-install-windows-powershell-30"></a>Windows PowerShell 3.0 をダウンロードしてインストールします。

[] Windows 8.1、Windows 8、Windows Server 2012 R2、または Windows Server 2012 を使用している場合は、既に Windows PowerShell 3.0 がある必要があります。このため、このアプリケーションはこれらのオペレーティング システムでプリインストールされています。 
  
Windows 7 または Windows Server 2008 R2 を実行している場合は、Windows PowerShell 3.0 も実行している可能性があります。ただし、バージョン 2.0、すなわちこれらのオペレーティング システムで元から提供されているバージョンを実行している可能性もあります。どのバージョンの Microsoft PowerShell を使用しているかを判別するには、お使いの Windows 7 または Windows Server 2008 R2 コンピューターで次を実行します。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックしてから、[ **Windows PowerShell**] をクリックします。
    
2. PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。
    
    ```
   Get-Host | Select-Object Version
   ```

3. 次のような情報がコンソール ウィンドウに表示されることになります。
    
    ```
    Version
    -------
    3.0
    ```

    返されたバージョン番号が 3.0 の場合は、Windows PowerShell 3.0 を実行しています。返されたバージョン番号が 3.0 でない場合は、Windows PowerShell 3.0 をインストールする必要があります。Windows PowerShell 3.0 を含んでいる Windows Management Framework 3.0 を、[Microsoft ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=34595)からダウンロードできます。
  
Windows PowerShell 3.0 がインストールされていることを検証した後、PowerShell がリモート スクリプトを実行するために構成されていることを確認する必要があります。これを実行するには、PowerShell を管理者として開始する必要があります。Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 で次を実行します。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。
    
2. [ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
Windows 8 を実行している場合は、代わりにこの手順を完了します。
  
1. チャーム バーにアクセスして、[ **検索**] をクリックしてから [ **Windows PowerShell**] を右クリックします。どの Windows 8 コンピューター (タッチ スクリーンまたはタッチ非対応スクリーン) 上でも、Windows キーを押したままで C をクリックすることによってすばやくチャーム バーにアクセスできます。
    
2. 画面の下部にあるツールバーで、[ **管理者として実行**] をクリックします。
    
3. [ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
PowerShell が実行されている状態になったら、リモート スクリプトの実行を許可するように実行ポリシーを変更する必要があります。PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
実行ポリシーが正しく構成されていることを確認するには、PowerShell プロンプトで次を入力してから ENTER を押します。
  
```
Get-ExecutionPolicy
```

次の値を取り戻したら、すべてが正しく構成されていることになります。
  
```
RemoteSigned
```

現在 Windows PowerShell 3.0 を正しく実行していない場合は Microsoft ダウンロード センターから Windows Management Framework 3.0 をダウンロードしてインストールする必要もあります。これは、Windows PowerShell 3.0 と Windows リモート管理 (WinRM) 3.0 を含んでいるインストール パッケージです。このインストール パッケージは、Windows 7 を実行していて Windows PowerShell 3.0 にまだ更新していない場合に必要となる可能性があります。Windows Server 2012、Windows Server 2012 R2、Windows 8、または Windows 8.1 を実行している場合は、Windows PowerShell 3.0 をインストールする必要はありません。Windows PowerShell 3.0 はこれらのオペレーティング システムでプレインストールされています。
  
Windows Management Framework 3.0 をインストールする前に、次を行います。
  
- インストール パッケージの正しいバージョンをダウンロードしたことを確認します。Windows 7 の 64 ビット バージョンを実行している場合は、ファイル Windows6.1-KB2506143-x64.msu をダウンロードします。Windows 7 の 32 ビット バージョンを実行している場合は、ファイル Windows6.1-KB2506143-x86.msu をダウンロードします。
    
- コンピューター上で Windows 7 を実行している場合は、Windows 7 Service Pack 1 をインストール済みであることを確認します。
    
どのバージョンの Windows を実行しているかわからない場合、または Windows 7 Service Pack 1 をインストール済みであるかわからない場合は、[ **スタート**] をクリックして、[ **コンピューター**] を右クリックしてから [ **プロパティ**] をクリックします。この情報は [システム] ダイアログ ボックスで報告されます。
  
Windows Management Framework 3.0 をインストールするには、次の手順を完了します。
  
1. .MSU インストール ファイルi ( **Windows6.1-KB2506143-x64.msu** または **Windows6.1-KB2506143-x86.msu**) をダブルクリックします。
    
2. [更新プログラムのダウンロードとインストール] ウィザードの [ **ライセンス条項をお読みください (1 / 1)**] ページで、[ **同意します**] をクリックします。
    
3. インストールが完了したら、[ **今すぐ再起動**] をクリックしてコンピューターを再起動します。
    
コンピューターが再起動した後に、Windows PowerShell が開始できることと、管理者の資格情報でアプリケーションが実行できることを検証します。その手順は次のとおりです。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。
    
2. [ユーザー アカウント制御] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
PowerShell コンソールが表示されたら、WinRM サービスが実行中で正しく構成されていることを検証する必要があります。サービスが実行されていることを検証するには、次のコマンドを PowerShell プロンプトに入力して ENTER を押します。
  
```
Get-Service winrm
```

WinRM サービスに関する情報が画面に表示されます。
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

サービスの状態が「実行中」を表すものでない場合は、次のコマンドを入力して ENTER を押すことによって WinRM サービスを開始します。
  
```
Start-Service winrm
```

サービスが開始した後、次のコマンドを実行して WinRM が基本認証を使用していることを確認します。
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

次のような情報が画面上に表示されます。
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

基本認証がある場合は、PowerShell を使用して、Skype のビジネスをオンラインに接続する準備が整ったら、true に設定されています。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Windows PowerShell 用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md) 

  
 