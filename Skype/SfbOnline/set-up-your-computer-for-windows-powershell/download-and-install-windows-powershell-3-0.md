---
title: "ダウンロードして、Windows PowerShell 3.0 をインストールする."
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: "ダウンロード、インストール、および Windows PowerShell 3.0 を使用して、Skype for Business Online に接続するためのリモート PowerShell セッションを作成します。"
ms.openlocfilehash: c3fddb71c677e602332adc5b564627969552d4c9
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="download-and-install-windows-powershell-30"></a>ダウンロードして、Windows PowerShell 3.0 をインストールする.

Windows 8.1、Windows 8、Windows Server 2012 R2 または Windows Server 2012 を使用している場合は、Windows PowerShell 3.0 既にが必要です。このアプリケーションは、これらのオペレーティング システムがあらかじめインストールされているためにです。 
  
Windows 7 または Windows Server 2008 R2 を実行している場合は、Windows PowerShell 3.0 を実行するも可能性があります。ただし、こともする可能性がありますが実行されているバージョン 2.0 代わりに、これらのオペレーティング システムに同梱されていたバージョンです。使用している Microsoft PowerShelll のバージョンを確認するのには、Windows 7 または Windows Server 2008 R2 のコンピューターに次を手順します。
  
1. [**スタート**] ボタン**すべてのプログラム**] をクリックして、[**アクセサリ**] をクリックして、 **Windows PowerShell**を**Windows PowerShell**] をクリックします。
    
2. PowerShell コンソールで、次のコマンドを入力し、[ENTER キーを押します。
    
    ```
   Get-Host | Select-Object Version
   ```

3. コンソール ウィンドウで、[次のような情報が表示されます。
    
    ```
    Version
    -------
    3.0
    ```

    返されるバージョン番号が 3.0 の場合は、Windows PowerShell 3.0 を実行しています。返されるバージョン番号が 3.0 でない場合は、Windows PowerShell 3.0 をインストールする必要があります。Windows PowerShell 3.0 が含まれている Windows Management Framework 3.0 は、 [Microsoft ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=34595)からダウンロードできます。
  
Windows PowerShell 3.0 がインストールされていることを確認した後、PowerShell がリモート スクリプトを実行するために構成されていることを確認してください。そのため、管理者として PowerShell を起動します。Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 では、次の操作を行います。
  
1. [**スタート**] ボタン**すべてのプログラム**] をクリックして、[**アクセサリ**] をクリックして、 **Windows PowerShell**、 **Windows PowerShell**を右クリックし、[**管理者として実行**] をクリックします。
    
2. [**ユーザー アカウント制御**] ダイアログ ボックスが表示されている場合は、管理者の資格情報の下で、PowerShell を実行することを確認するのに**[はい]**ををクリックします。
    
Windows 8 を実行している場合は、この手順を実行します。
  
1. チャーム バーのアクセス、**検索**] をクリックし、 **Windows PowerShell**を右クリックします。チャーム バーで、任意の Windows 8 コンピューター (タッチ スクリーンまたは非タッチ画面) は、Windows キーを押しながら C キーを押して、すばやくアクセスできます。
    
2. ツールバーで、画面の下部にある、**管理者として実行**] をクリックします。
    
3. [**ユーザー アカウント制御**] ダイアログ ボックスが表示されている場合は、管理者の資格情報の下で、PowerShell を実行することを確認するのに**[はい]**ををクリックします。
    
PowerShell の実行後に、リモート スクリプトの実行を許可する実行ポリシーを変更する必要があります。PowerShell コンソールで、次のコマンドを入力し、[ENTER キーを押します。
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
実行ポリシーが正しく構成されていることを確認するには、PowerShell のプロンプトで、次を入力し、し、ENTER キーを押します。
  
```
Get-ExecutionPolicy
```

次の値を戻ることがある場合、[すべてのアイテムが正しく構成されています。
  
```
RemoteSigned
```

Windows PowerShell 3.0 を現在実行されていない場合も、ダウンロードして、Microsoft ダウンロード センターから Windows Management Framework 3.0 をインストールする必要があります。これは、Windows PowerShell 3.0 および Windows リモート管理 (WinRM) 3.0 を含むインストール パッケージです。Windows 7 を実行し、Windows PowerShell 3.0 に更新がいない場合は、このインストール パッケージが必要になる場合があります。Windows Server 2012、Windows Server 2012 R2、Windows 8 または Windows 8.1 を実行している場合は、Windows PowerShell 3.0 をインストールする必要がありますいけません。Windows PowerShell 3.0 は、これらのオペレーティング システムであらかじめインストールされているできます。
  
Windows Management Framework 3.0 をインストールするには: する前に
  
- 適切なバージョンのインストール パッケージをダウンロードすることを確認します。64 ビット バージョンの Windows 7 を実行している場合は、Windows6.1-KB2506143-x64.msu ファイルをダウンロードします。32 ビット バージョンの Windows 7 を実行している場合は、Windows6.1-KB2506143-x86.msu ファイルをダウンロードします。
    
- お使いのコンピューターで Windows 7 を実行している場合は、Windows 7 の Service Pack 1 がインストールされていることを確認します。
    
不明な場合 Windows のバージョンを実行しているかが不明な Windows 7 の Service Pack 1 のインストールを**開始**] をクリックして、**コンピューター**を右クリックし、[**プロパティ**] をクリックします。[システム] ダイアログ ボックスでこの情報が報告されます。
  
Windows Management Framework 3.0 をインストールするのには、次の手順を行います。
  
1. ダブルクリックします。MSU インストール ファイル ( **Windows6.1-KB2506143-x64.msu**または**Windows6.1-KB2506143-x86.msu**)。
    
2. ダウンロードおよび更新プログラムのインストール ウィザードで、**この使用許諾条項 (1/1) の読み取り**] ページで、[**同意**] をクリックします。
    
3. インストールが完了したら、 **[今すぐ再起動**お使いのコンピューターを再起動するのにをクリックします。
    
コンピューターの再起動後に Windows PowerShell を開始することを管理者の資格情報、アプリケーションを実行できることを確認します。これを行うには。
  
1. [**スタート**] ボタン**すべてのプログラム**] をクリックして、[**アクセサリ**] をクリックして、 **Windows PowerShell**、 **Windows PowerShell**を右クリックし、[**管理者として実行**] をクリックします。
    
2. 管理者の資格情報で PowerShell を実行する場合は、ユーザー アカウント制御] ダイアログ ボックスが表示されたら、 **[はい**] をクリックしてことを確認します。
    
PowerShell コンソールが表示されたらは、WinRM サービスが実行されていると正しく構成されていることを確認してください。サービスが実行されていることを確認するには、PowerShell のプロンプトで、次のコマンドを入力し、ENTER キーを押します。
  
```
Get-Service winrm
```

WinRM サービスについての情報が、[画面に表示されます。
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

サービスの状態ではない「を実行している」場合、は、次のコマンドを入力し、ENTER を押すことによって WinRM サービスを開始します。
  
```
Start-Service winrm
```

サービスを開始した後、WinRM が基本認証を使用しているかどうかを確認するには、次のコマンドを実行します。
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

画面に表示されるには、次のような情報が表示されます。
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

場合は、Skype for Business Online に接続する PowerShell を使用する準備ができたら、基本認証を true に設定されています。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック
[Windows PowerShell の自分のコンピューターを設定します。](set-up-your-computer-for-windows-powershell.md) 
