---
title: Skype for Business Server 2015 管理シェル
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: ビジネス サーバー管理シェルの Skype では、サーバーの管理と管理のコマンド ライン インターフェイスを提供します。 Windows PowerShell の上に構築し、Skype と従来の Lync server 製品に固有のコマンドレットが管理の包括的なセットが含まれています。
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a>Skype for Business Server 2015 管理シェル
 
ビジネス サーバー管理シェルの Skype では、サーバーの管理と管理のコマンド ライン インターフェイスを提供します。 Windows PowerShell の上に構築し、Skype と従来の Lync server 製品に固有のコマンドレットが管理の包括的なセットが含まれています。
  
Windows PowerShell を使用すると、Microsoft アプリケーションをコマンドラインから管理できます。 コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。 Windows PowerShell は、2006 年の後半で Windows オペレーティング システム用のダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理用のコマンド ライン インターフェイスとして採用されました。 それは、Lync Server 2010 から Lync と Skype のサーバーを含む、Microsoft サーバー製品の大部分に組み込まれています。 700 を超える Lync と Skype の特定のコマンドレットがビジネスのサーバー管理シェルの Skype で利用できます。
  
> [!NOTE]
> コマンドレット参照のビジネス用の Skype は、docs.microsoft.com に移動します。以下のリンクをクリックするとクリックすると、新しい docs.microsoft.com ページです。 そのコンテンツはオープン ソースとなり、GitHub を通したコミュニティへの投稿として利用できるようになりました。 投稿に興味はありますか? ここでは、リポジトリの索引にある readme ファイルを確認します。[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
ビジネス サーバー 2015 の Skype は、Skype をビジネス サーバー管理シェルには、Skype を使用してビジネスのサーバーを管理する管理者を有効にする 700 以上のコマンドレットで出荷されます。 以下のようなコマンドを入力すると、コマンドレットのヘルプを、コマンド ラインから直接取得することができます。
  
```
Get-Help New-CsVoicePolicy -Full
```

上記のコマンドは、**新しい CsVoicePolicy**コマンドレットの完全なヘルプを取得します。 別のコマンドレットのヘルプを表示するには、ヘルプを取得するコマンドレットの名前を持つ**新規 CsVoicePolicy**を置き換えてください。
  
Skype for Business Server の管理に使用できるすべてのコマンドレットの一覧を取得するには、シェル コマンド プロンプトで以下を入力します。 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



ビジネス サーバー用 Skype で Windows PowerShell について理解すること:
  
- Skype ビジネス サーバー コマンドレットを実行するには、ビジネス サーバー管理シェルには、Skype を開きます。
    
    > [!CAUTION]
    > ビジネス サーバー管理シェルには、Skype ではなく、Windows PowerShell のウィンドウを開いた場合既定では、できないことがあります Skype コマンドレットを実行します。 Skype Windows PowerShell 内からのビジネス サーバー コマンドレットを実行する Windows PowerShell コマンド プロンプトで最初に次を入力します >。`Import-Module SkypeforBusiness`
  
- ビジネス サーバー エンタープライズ版フロント エンド サーバーまたは Standard Edition サーバーのすべての Skype のビジネス サーバー管理シェルの Skype が自動的にインストールします。
    
- ビジネス サーバー管理シェルのヘルプ コンテンツの Skype を更新するには、[更新プログラムのヘルプ](https://technet.microsoft.com/en-us/library/hh849720.aspx)のコマンドレットを実行します。 更新ヘルプのコマンドレットでは、Skype ビジネス コマンドレットの更新など、コンピューターにインストールされているモジュールのすべての利用可能な最新のヘルプ ファイルをダウンロードしています。
    
    既定では、**更新プログラムのヘルプ**のコマンドレットは、Skype のビジネス サーバーがインストールされているすべてのモジュールを更新します。 一部のモジュールだけを更新する場合は、コマンドレットのスコープを制限する_モジュール_のパラメーターを使用することができます。 次の例では、ビジネス モジュールの Skype のみを更新します。
    
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
    

