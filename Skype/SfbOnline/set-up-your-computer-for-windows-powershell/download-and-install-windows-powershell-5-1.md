---
title: Windows PowerShell 5.1 をダウンロードしてインストールする
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Windows PowerShell 5.1 をダウンロード、インストール、および使用して、Skype for Business Online に接続するリモート PowerShell セッションを作成します。
ms.openlocfilehash: 227023d5c86b99a66ecdbdabd3b2973d0383a534
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831155"
---
# <a name="download-and-install-windows-powershell-51"></a>Windows PowerShell 5.1 をダウンロードしてインストールする

Windows 10 記念の更新プログラムまたは Windows Server 2016 を使用している場合は、既に Windows PowerShell 5.1 を持っている必要があります。 このため、このアプリケーションはこれらのオペレーティング システムでプリインストールされています。
  
使用している Microsoft PowerShelll のバージョンを確認するには、Windows 7 または windows Server 2008 R2 または Windows Server 2012 コンピューターで次の操作を行います。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックしてから、[ **Windows PowerShell**] をクリックします。
    
2. PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. 次のような情報がコンソール ウィンドウに表示されることになります。
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    返されるバージョン番号が5.1 の場合は、Windows PowerShell 5.1 を実行しています。 返されるバージョン番号が5.1 ではない場合は、Windows PowerShell 5.1 をインストールする必要があります。 Windows PowerShell 5.1 を含む Windows Management Framework 5.1 は、 [Microsoft ダウンロードセンター](https://www.microsoft.com/en-us/download/details.aspx?id=54616)からダウンロードできます。
  
Windows PowerShell 5.1 がインストールされていることを確認したら、リモートスクリプトを実行するように PowerShell が構成されていることを確認する必要があります。 これを実行するには、PowerShell を管理者として開始する必要があります。 Windows 7、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 で次を実行します。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。
    
2. [ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
Windows 8 を実行している場合は、代わりにこの手順を完了します。
  
1. チャーム バーにアクセスして、[ **検索**] をクリックしてから [ **Windows PowerShell**] を右クリックします。どの Windows 8 コンピューター (タッチ スクリーンまたはタッチ非対応スクリーン) 上でも、Windows キーを押したままで C をクリックすることによってすばやくチャーム バーにアクセスできます。
    
2. 画面の下部にあるツールバーで、[ **管理者として実行**] をクリックします。
    
3. [ **ユーザー アカウント制御**] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
PowerShell が実行されている状態になったら、リモート スクリプトの実行を許可するように実行ポリシーを変更する必要があります。PowerShell コンソールで、次のコマンドを入力してから ENTER を押します。
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 上記のコマンドを実行すると、次のエラーメッセージが表示されることがあります: > *set-executionpolicy: レジストリキーへ\\の\\アクセス\\HKEY_LOCAL_MACHINE\\、\\Microsoft\\powershell 1 ShellIds micrsoft soft soft soft soft soft soft soft soft soft the powershell ' が拒否さ*れています。 このエラーメッセージは、通常、管理者の資格情報で PowerShell を実行していない場合に発生します。 PowerShell のセッションを終了し、管理者として新しいセッションを開始します。
 
実行ポリシーが正しく構成されていることを確認するには、PowerShell プロンプトで次を入力してから ENTER を押します。
  
```PowerShell
Get-ExecutionPolicy
```

次の値を取り戻したら、すべてが正しく構成されていることになります。
  
`RemoteSigned`

現在 Windows PowerShell 5.1 を実行していない場合は、Microsoft ダウンロードセンターから Windows Management Framework 5.1 をダウンロードしてインストールする必要もあります。 これは、Windows PowerShell 5.1 および Windows リモート管理 (WinRM) 3.0 を含むインストールパッケージです。 たとえば、Windows 7 SP1 を実行していて、Windows PowerShell 5.1 にまだ更新されていない場合は、このインストールパッケージが必要になることがあります。 Windows Server 2016 または Windows 10 記念日更新を実行している場合は、Windows PowerShell 5.1 をインストールする必要はありません。 Windows PowerShell 5.1 は、これらのオペレーティングシステムにプレインストールされています。
  
Windows Management Framework 5.1 をインストールする前に、次の操作を行います。
  
- インストール パッケージの正しいバージョンをダウンロードしたことを確認します。 64ビット版の Windows 7 SP1 を実行している場合は、Win7AndW2K8R2-KB3191566-x64 ファイルをダウンロードします。 32ビットバージョンの Windows 7 を実行している場合は、Win7-KB3191566-x86 ファイルをダウンロードします。
    
- コンピューター上で Windows 7 を実行している場合は、Windows 7 Service Pack 1 をインストール済みであることを確認します。

どのバージョンの Windows を実行しているかわからない場合、または Windows 7 Service Pack 1 をインストール済みであるかわからない場合は、[ **スタート**] をクリックして、[ **コンピューター**] を右クリックしてから [ **プロパティ**] をクリックします。この情報は [システム] ダイアログ ボックスで報告されます。
  
Windows Management Framework 5.1 をインストールするには、「 [WMF 5.1 をインストールして構成](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)する」の手順を実行します。
  
コンピューターが再起動した後に、Windows PowerShell が開始できることと、管理者の資格情報でアプリケーションが実行できることを検証します。その手順は次のとおりです。
  
1. [ **スタート**]、[ **すべてのプログラム**]、[ **アクセサリ**]、[ **Windows PowerShell**] の順にクリックして、[ **Windows PowerShell**] を右クリックし、[ **管理者として実行**] をクリックします。
    
2. [ユーザー アカウント制御] ダイアログ ボックスが表示される場合、[ **はい**] をクリックして管理者の資格情報の下で PowerShell を実行することを確認します。
    
PowerShell コンソールが表示されたら、WinRM サービスが実行中で正しく構成されていることを検証する必要があります。サービスが実行されていることを検証するには、次のコマンドを PowerShell プロンプトに入力して ENTER を押します。
  
```PowerShell
Get-Service winrm
```

WinRM サービスに関する情報が画面に表示されます。
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

サービスの状態が「実行中」を表すものでない場合は、次のコマンドを入力して ENTER を押すことによって WinRM サービスを開始します。
  
```PowerShell
Start-Service winrm
```

サービスが開始した後、次のコマンドを実行して WinRM が基本認証を使用していることを確認します。
  
```PowerShell
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

基本認証が true に設定されている場合は、PowerShell を使用して Skype for Business Online に接続する準備ができています。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック
[Windows PowerShell 用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md) 

  
 
