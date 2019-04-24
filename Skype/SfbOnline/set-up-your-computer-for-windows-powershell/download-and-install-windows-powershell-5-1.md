---
title: ダウンロードし、Windows PowerShell の 5.1 をインストールします。
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
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
- PowerShell
- LIL_Placement
description: ダウンロード、インストール、および Windows PowerShell の 5.1 を使用して Skype のビジネスをオンラインに接続するリモート PowerShell セッションを作成します。
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198070"
---
# <a name="download-and-install-windows-powershell-51"></a>ダウンロードし、Windows PowerShell の 5.1 をインストールします。

10 記念日の更新プログラムを Windows または Windows Server 2016 を使用する場合は、Windows PowerShell の 5.1 が既に必要があります。 このため、このアプリケーションはこれらのオペレーティング システムでプリインストールされています。
  
使用している Microsoft PowerShelll のバージョンを確認するには、Windows 7 または Windows Server 2008 R2 または Windows Server 2012 コンピューターで次の操作を行います。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックしてから、[ **Windows PowerShell**] をクリックします。
    
2. PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。
    
   ```
   Get-Host | Select-Object Version
   ```

3. 次のような情報がコンソール ウィンドウに表示されることになります。
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    返されたバージョン番号が 5.1 である場合は、Windows PowerShell の 5.1 を実行しています。 返されたバージョン番号は 5.1 ではない場合が、Windows PowerShell の 5.1 をインストールする必要があります。 Windows PowerShell の 5.1 が含まれている Windows Management Framework 5.1 は、 [Microsoft ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=54616)からダウンロードできます。
  
Windows PowerShell の 5.1 がインストールされていることを確認して後、は、リモート スクリプトを実行するため、PowerShell が構成されていることを確認の操作を行う必要があります。 これを実行するには、PowerShell を管理者として開始する必要があります。 Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 で次を実行します。
  
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
> 上記のコマンドを実行すると、次エラー メッセージ: _gt*セット ExecutionPolicy が表示される可能性があります: レジストリ キーへのアクセス ' HKEY_LOCAL_MACHINE\\ソフトウェア\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' が拒否されました*。 このエラー メッセージは、通常、PowerShell が管理者の資格情報で実行されていない場合に発生します。 PowerShell セッションを閉じるし、管理者は新しいセッションを開始します。
 
実行ポリシーが正しく構成されていることを確認するには、PowerShell プロンプトで次を入力してから ENTER を押します。
  
```
Get-ExecutionPolicy
```

次の値を取り戻したら、すべてが正しく構成されていることになります。
  
`RemoteSigned`

Windows PowerShell の 5.1 を現在実行されていない場合、ダウンロードして Microsoft ダウンロード センターから Windows Management Framework 5.1 をインストールする必要もあります。 これは、Windows PowerShell の 5.1 と Windows リモート管理 (WinRM) 3.0 を含むインストール パッケージです。 Windows 7 SP1 を実行しているし、Windows PowerShell の 5.1 を更新していない場合、たとえば場合、は、このインストール パッケージが必要になる可能性があります。 Windows Server 2016、または Windows 10 記念日の更新プログラムを実行している場合は、Windows PowerShell の 5.1 をインストールする必要があるいけません。 Windows PowerShell の 5.1 は、これらのオペレーティング システムにプレインストールされているものです。
  
Windows Management Framework 5.1 をインストール: する前に
  
- インストール パッケージの正しいバージョンをダウンロードしたことを確認します。 Windows 7 SP1 の 64 ビット バージョンを実行している場合は、Win7AndW2K8R2-KB3191566-x64.ZIP のファイルをダウンロードします。 Windows 7 の 32 ビット バージョンを実行している場合は、Win7-KB3191566-x86.ZIP のファイルをダウンロードします。
    
- コンピューター上で Windows 7 を実行している場合は、Windows 7 Service Pack 1 をインストール済みであることを確認します。

どのバージョンの Windows を実行しているかわからない場合、または Windows 7 Service Pack 1 をインストール済みであるかわからない場合は、[ **スタート**] をクリックして、[ **コンピューター**] を右クリックしてから [ **プロパティ**] をクリックします。この情報は [システム] ダイアログ ボックスで報告されます。
  
Windows Management Framework 5.1 をインストールするには、[インストールと構成の WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)での手順を実行します
  
コンピューターが再起動した後に、Windows PowerShell が開始できることと、管理者の資格情報でアプリケーションが実行できることを検証します。その手順は次のとおりです。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。
    
2. [ユーザー アカウント制御] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
PowerShell コンソールが表示されたら、WinRM サービスが実行中で正しく構成されていることを検証する必要があります。サービスが実行されていることを検証するには、次のコマンドを PowerShell プロンプトに入力して ENTER を押します。
  
```
Get-Service winrm
```

WinRM サービスに関する情報が画面に表示されます。
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

サービスの状態が「実行中」を表すものでない場合は、次のコマンドを入力して ENTER を押すことによって WinRM サービスを開始します。
  
```
Start-Service winrm
```

サービスが開始した後、次のコマンドを実行して WinRM が基本認証を使用していることを確認します。
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

次のような情報が画面上に表示されます。
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

基本認証がある場合は、PowerShell を使用して、Skype のビジネスをオンラインに接続する準備が整ったら、true に設定されています。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック
[Windows PowerShell 用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md) 

  
 
