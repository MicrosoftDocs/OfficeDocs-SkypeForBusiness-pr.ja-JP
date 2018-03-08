---
title: "ダウンロードして、Skype for Business Online コネクタ モジュールをインストールします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: "ダウンロード、インストール、および Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Skype for Business Online コネクタを使用します。 "
ms.openlocfilehash: e95b65d62434a6ea7a52714536b1b11d47f08a8c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>ダウンロードして、Skype for Business Online コネクタ モジュールをインストールします。

Skype for Business Online コネクタ モジュールでは、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができる**新しい CsOnlineSession**コマンドレットが含まれています。このモジュールでは、「 [skype for Business Online 管理を Windows PowerShell を使用して、コンピューター設定する](set-up-your-computer-for-windows-powershell.md)詳細については)、64 ビット コンピューター以外ではは、 [https:// に Microsoft ダウンロード センターからダウンロードできます。www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)します。SkypeOnlinePowershell.exe ファイルをダウンロードしてから、次の手順を実行します。
  
1. **SkypeOnlinePowershell.exe**ファイルをダブルクリックします。
    
2. Skype for Business Online では、Windows PowerShell のセットアップ ウィザードの**Microsoft ソフトウェア ライセンス条項**] ページは、**使用許諾契約書の条項に同意します**] を選択し、[**インストール**] をクリックします。場合は、 **[ユーザー アカウント制御**] ダイアログ ボックスが表示されたら、 **[はい**インストールをクリックします。
    
3. [ **Skype for Business Online、Windows PowerShell モジュールの完了**] ページで、[**完了**] をクリックします。
    
セットアップ プログラムは、Skype for Business Online コネクタ モジュール (と**新規 CsOnlineSession**コマンドレット) を自分のコンピューターにコピーします。モジュールにアクセスするには、管理者の資格情報は、[Windows PowerShell セッションを開始し、次のコマンドを実行します。
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Windows PowerShell を起動するたびに、このコマンドを入力しない場合は、Windows PowerShell の自分のプロファイルにコマンドを追加できます。そのため、Windows PowerShell のプロンプトで、次のコマンドを入力し、し、ENTER キーを押します。
  
```
notepad.exe $profile
```

 メモ帳が表示されたら、(設定されている場合) のプロファイルに存在するコマンドの下部に次の行を追加します。
  
```
Import-Module SkypeOnlineConnector
```

ファイルを保存します。次に、Windows PowerShell を起動したとき、Skype for Business Online コネクタ モジュールが自動的にインポートされます。エラー メッセージが表示されますとなるモジュールを読み込むことができませんが、Windows PowerShell が管理者の資格情報で実行されていない場合。
  
Skype for Business Online コネクタ モジュールをインストールするには、SkypeOnlinePowershell.exe もインストールが 3 つの他のコンポーネント: 1)、身元サービス クライアント ランタイム ライブラリ (IDCRL)、skype for Business クライアントの認証を処理します。オンラインです。2) .NET framework 4.5 です。3)、Microsoft Visual C++ 2012 再頒布可能コンポーネント (x64) パッケージ (バージョン 11.0.50727)。.NET framework 4.5 では、作成したり、Windows PowerShell を含む、.NET アプリケーションを実行するために使用するインフラストラクチャを提供します。Microsoft Visual Studio 2012 がインストールされていないコンピューターの Visual C ランタイム コンポーネントを視覚的な C++ 再頒布可能コンポーネントにインストールします。
  
現在コンピューターにインストールされているコネクタ モジュールのバージョン番号を確認するには、[コントロール パネルを開きます**プログラムと機能**] を開く、 **Skype for Business Online、Windows PowerShell モジュール**のバージョン番号を確認します。
  
## <a name="related-topics"></a>関連トピック
[Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。](set-up-your-computer-for-windows-powershell.md)
