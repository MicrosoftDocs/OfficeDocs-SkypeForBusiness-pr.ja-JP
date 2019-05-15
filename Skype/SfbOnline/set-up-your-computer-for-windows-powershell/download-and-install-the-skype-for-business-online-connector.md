---
title: Skype for Business Online Connector モジュールをダウンロードしてインストールする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036694"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Skype for Business Online Connector モジュールをダウンロードしてインストールする

[] Skype for Business Online Connector モジュール には、 **New-CsOnlineSession** Windows PowerShell に接続するリモート Skype for Business Online セッションを作成できるようにする コマンドレットが含まれます。 Microsoft ダウンロード センターからダウンロードできます (を参照してください[Windows PowerShell を使用してオンライン ビジネスの管理のための Skype には、コンピューターの設定](set-up-your-computer-for-windows-powershell.md)の詳細については) 64 ビット コンピューターでのみサポートされて、このモジュールは、 [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366)。 SkypeOnlinePowershell.exe ファイルをダウンロードしてから、次の手順を完了します。
  
1. **SkypeOnlinePowershell.exe** ファイルをダブルクリックします。
    
2. In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.
    
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

  
 
