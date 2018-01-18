---
title: "Skype for Business Online Connector モジュールをダウンロードしてインストールする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: b95b41937fea2ec87cb484cf557d85dcb3a77a8e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Skype for Business Online Connector モジュールをダウンロードしてインストールする

ビジネス オンライン コネクタ モジュールの Skype には、Skype のビジネスをオンラインに接続するリモートの Windows PowerShell セッションを作成するのには、**新しい CsOnlineSession**のコマンドレットが含まれています。 (を参照してください[Windows PowerShell を使用してオンライン ビジネスの管理のための Skype には、コンピューターの設定](set-up-your-computer-for-windows-powershell.md)の詳細については) 64 ビット コンピューターでのみサポートされているが、このモジュールは、 [https://、マイクロソフト ダウンロード センターからダウンロードできます。www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。 SkypeOnlinePowershell.exe ファイルをダウンロードし、し次の手順を実行します。
  
1. **SkypeOnlinePowershell.exe** ファイルをダブルクリックします。
    
2. ビジネス オンラインの Skype、Windows PowerShell のセットアップ ウィザードで、[**マイクロソフト ソフトウェア ライセンス条項**] ページで、[**使用許諾契約の条項に同意**でし、[**インストール**] をクリックします。 場合は、[**ユーザー アカウント制御**] ダイアログ ボックスが表示されたら、 **[はい**インストールを続行するをクリックします。
    
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
  
## <a name="related-topics"></a>関連トピック
[Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します](set-up-your-computer-for-windows-powershell.md)
