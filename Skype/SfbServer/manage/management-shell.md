---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: ビジネス サーバー管理シェルの Skype では、サーバーの管理と管理のコマンド ライン インターフェイスを提供します。 Windows PowerShell の上に構築し、Skype と従来の Lync server 製品に固有のコマンドレットが管理の包括的なセットが含まれています。
ms.openlocfilehash: 1daf83ea401501f6607a30aa7710f1d338c47af9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888346"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル
 
ビジネス サーバー管理シェルの Skype では、サーバーの管理と管理のコマンド ライン インターフェイスを提供します。 Windows PowerShell の上に構築し、Skype と従来の Lync server 製品に固有のコマンドレットが管理の包括的なセットが含まれています。
  
Windows PowerShell を使用すると、Microsoft アプリケーションをコマンドラインから管理できます。 コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。 Windows PowerShell は、2006 年の後半で Windows オペレーティング システム用のダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理用のコマンド ライン インターフェイスとして採用されました。 それは、Lync Server 2010 から Lync と Skype のサーバーを含む、Microsoft サーバー製品の大部分に組み込まれています。 700 を超える Lync と Skype の特定のコマンドレットがビジネスのサーバー管理シェルの Skype で利用できます。
  
> [!NOTE]
> コマンドレット参照のビジネス用の Skype は、docs.microsoft.com に移動します。 以下のリンクをクリックするとクリックすると、新しい docs.microsoft.com ページです。 コンテンツは、ここでは GitHub から差し引かれるとの利用可能なコミュニティを開いている投稿です。 寄贈したいですか。 ここでは、リポジトリの索引にある readme ファイルを確認します。[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
ビジネス サーバー管理シェルには、Skype を使用してビジネス サーバーの Skype を管理する管理者を有効にするコマンドレットが 700 を超えるビジネス サーバーの Skype が同梱されています。 以下のようなコマンドを入力すると、コマンドレットのヘルプを、コマンド ラインから直接取得することができます。
  
```
Get-Help New-CsVoicePolicy -Full
```

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。 別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。
  
Skype for Business Server の管理に使用できるすべてのコマンドレットの一覧を取得するには、シェル コマンド プロンプトで以下を入力します。 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



ビジネス サーバー用 Skype で Windows PowerShell について理解すること:
  
- Skype ビジネス サーバー コマンドレットを実行するには、ビジネス サーバー管理シェルには、Skype を開きます。
    
    > [!CAUTION]
    > ビジネス サーバー管理シェルには、Skype ではなく、Windows PowerShell のウィンドウを開いた場合既定では、できないことがあります Skype コマンドレットを実行します。 Skype Windows PowerShell 内からのビジネス サーバー コマンドレットを実行する Windows PowerShell コマンド プロンプトで最初に、次の入力: _gt`Import-Module SkypeforBusiness`
  
- ビジネス サーバー エンタープライズ版フロント エンド サーバーまたは Standard Edition サーバーのすべての Skype のビジネス サーバー管理シェルの Skype が自動的にインストールします。
    
- ビジネス サーバー管理シェルのヘルプ コンテンツの Skype を更新するには、[更新プログラムのヘルプ](https://technet.microsoft.com/en-us/library/hh849720.aspx)のコマンドレットを実行します。 更新ヘルプのコマンドレットでは、Skype ビジネス コマンドレットの更新など、コンピューターにインストールされているモジュールのすべての利用可能な最新のヘルプ ファイルをダウンロードしています。
    
    既定では、**更新プログラムのヘルプ**のコマンドレットは、Skype のビジネス サーバーがインストールされているすべてのモジュールを更新します。 特定のモジュールのみ更新する場合は、_Module_ パラメーターを使用してこのコマンドレットのスコープを制限できます。 次の例では、ビジネス モジュールの Skype のみを更新します。
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    インターネットに接続されていないサーバーのヘルプを更新する場合は、ヘルプの最新バージョンを取得し、指定された場所に保存する[保存ヘルプ](https://technet.microsoft.com/en-us/library/hh849724.aspx)コマンドレットを使用することができます。 選択した場所から更新済みのヘルプを表示するのにはインターネットに接続されていないサーバー上_で見つかった_パラメーターを使用して、**更新プログラムのヘルプ**のコマンドレットを使用できます。 次の使用例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有からビジネス モジュールの Skype のヘルプを更新する方法を示しています。
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    詳細については、[更新可能なヘルプについて](https://technet.microsoft.com/library/hh847735.aspx)を参照してください。
    
    > [!NOTE]
    > リモート PowerShell を使用している場合は、ファイアウォール経由の通信を許可する必要があります。 PowerShell リモート処理を使用するポートの詳細についてを参照してください[どのようなポートは PowerShell リモート処理の使用ですか?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)です。
    

