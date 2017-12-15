---
title: "Skype for Business Online Connector モジュールをダウンロードしてインストールする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
description: "Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
"
---

# Skype for Business Online Connector モジュールをダウンロードしてインストールする

Skype for Business Online Connector モジュール には、 **New-CsOnlineSession** Windows PowerShell に接続するリモート Skype for Business Online セッションを作成できるようにする コマンドレットが含まれます。このモジュールは、64 ビットのコンピューターでのみサポートされ ([Windows PowerShell を使用して Business Online の管理のため、skype お使いのコンピューターを設定する.](set-up-your-computer-for-skype-for-business-online-management-using-windows-powe.md) を参照)、[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366) にある Microsoft ダウンロード センター からダウンロードできます。SkypeOnlinePowershell.exe ファイルをダウンロードしてから、次の手順を完了します。
  
1. **SkypeOnlinePowershell.exe** ファイルをダブルクリックします。
    
2. Skype for Business Online で、Windows PowerShell セットアップ ウィザードの [ ** マイクロソフト ソフトウェア ライセンス条項**] ページで、[ **使用許諾契約書に同意します**] を選択してから、[ **インストール**] をクリックします。[ **ユーザー アカウント制御**] ダイアログ ボックスが表示された場合は、[ **はい**] をクリックしてインストールを続行します。
    
3. [ **Completed the Skype for Business Online, Windows PowerShell Module (Skype for Business Online、Windows PowerShell Module の完了)**] ページで、[ **完了**] をクリックします。
    
セットアップ プログラムが Skype for Business Online Connector モジュール (および **New-CsOnlineSession** コマンドレット) をコンピューターにコピーします。モジュールにアクセスするには、Windows PowerShell セッションを管理者の資格情報で開始してから、次のコマンドを実行します。
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

このコマンドを Windows PowerShell の開始時に毎回入力しないようにする場合に、そのコマンドを Windows PowerShell プロファイルに追加することができます。これを行うには、Windows PowerShell プロンプトで次のコマンドを入力してから ENTER を押します。
  
```
notepad.exe $profile
```

Notepad が表示されたら、(該当する場合は) 既にプロファイル内にあるコマンドの最下部に次の行を追加します。
  
```
Import-Module SkypeOnlineConnector
```

ファイルを保存します。次回の Windows PowerShell の開始時に、Skype for Business Online Connector モジュール が自動的にインポートされます。管理者の資格情報で Windows PowerShell を実行していない場合は、エラー メッセージが表示され、モジュールがロードされないことに留意してください。
  
Skype for Business Online Connector モジュール のインストールに加えて、SkypeOnlinePowershell.exe は、1) Skype for Business Online に対するクライアント認証を処理する Identity Service Client Runtime Library (IDCRL)、2) .NET Framework 4.5、および 3) Microsoft Visual C++ 2012 再頒布可能パッケージ (x64) (バージョン 11.0.50727) という 3 つの追加コンポーネントもインストールします。NET Framework 4.5 は、Windows PowerShell を含む .NET アプリケーションを構築して実行するために使われるインフラストラクチャを提供します。Visual C++ 再頒布可能パッケージは、Microsoft Visual Studio 2012 がインストールされていないコンピューターのために Visual C++ ランタイム コンポーネントをインストールします。
  
お使いのコンピューターに現在インストールされている Connector モジュールのバージョン番号を検証するには、[ **プログラムと機能** ] を開いて、 **Skype for Business Online、Windows PowerShell Module** のバージョン番号を確認してください。
  

