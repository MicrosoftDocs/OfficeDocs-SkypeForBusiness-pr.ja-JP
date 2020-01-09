---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 管理シェルには、サーバー管理と管理のためのコマンドラインインターフェイスが用意されています。 これは Windows PowerShell で構築されており、Skype および従来の Lync server 製品に固有の一連の管理と管理のコマンドレットが含まれています。
ms.openlocfilehash: 4890194824caaea771d31e008d4546d871d0da8a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991592"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル
 
Skype for Business Server 管理シェルには、サーバー管理と管理のためのコマンドラインインターフェイスが用意されています。 これは Windows PowerShell で構築されており、Skype および従来の Lync server 製品に固有の一連の管理と管理のコマンドレットが含まれています。
  
Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。 コマンド ライン環境、製品固有のコマンド、完全なスクリプト言語が用意されています。 Windows PowerShell は、最初に2006の Windows オペレーティングシステムのダウンロード可能なリリースとして導入されましたが、Microsoft Exchange Server 2007 の管理のためのコマンドラインインターフェイスとして採用されています。 Lync Server 2010 で始まる Lync および Skype サーバーを含むほとんどの Microsoft サーバー製品に組み込まれています。 Skype for Business Server 管理シェルでは、700の Lync と Skype 固有のコマンドレットを利用できます。
  
> [!NOTE]
> Skype for Business コマンドレットリファレンスは docs.microsoft.com に移動されました。 以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。 これでコンテンツが公開され、GitHub を通じてコミュニティの投稿に使用できるようになりました。 投稿に興味をお持ちですか? ここでは、リポジトリ内の README を確認します。[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server には、管理者が skype for Business Server Management Shell を使って Skype for Business Server を管理できるようにするための700コマンドレットが付属しています。 以下のようなコマンドを入力すると、コマンドレットのヘルプを、コマンド ラインから直接取得することができます。
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。 別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。
  
Skype for Business Server の管理に使用できるすべてのコマンドレットの一覧を取得するには、シェル コマンド プロンプトで以下を入力します。 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Skype for Business Server での Windows PowerShell について知っておくべきこと:
  
- Skype for Business Server コマンドレットを実行するには、Skype for Business Server 管理シェルを開きます。
    
    > [!CAUTION]
    > Skype for Business Server 管理シェルではなく、Windows PowerShell ウィンドウを開いた場合、既定では、Skype コマンドレットを実行することはできません。 Windows PowerShell 内から Skype for Business Server コマンドレットを実行するには、まず、Windows PowerShell コマンドプロンプトで次のように入力します。 >`Import-Module SkypeforBusiness`
  
- Skype for business Server 管理シェルは、すべての Skype for Business Server Enterprise Edition のフロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。
    
- Skype for Business Server 管理シェルのヘルプコンテンツは、 [update-ヘルプ](https://technet.microsoft.com/en-us/library/hh849720.aspx)コマンドレットを実行して更新できます。 更新プログラムのヘルプコマンドレットは、お使いのコンピューターにインストールされているすべてのモジュールで利用できる最新のヘルプファイルをダウンロードしてインストールします。これには、Skype for Business コマンドレットの更新が含まれます。
    
    既定では、[**更新] ヘルプ**コマンドレットによって、Skype For business Server にインストールされているすべてのモジュールが更新されます。 特定のモジュールのみ更新する場合は、_Module_ パラメーターを使用してこのコマンドレットのスコープを制限できます。 次の例では、Skype for Business モジュールのみが更新されます。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は、[ヘルプの[保存](https://technet.microsoft.com/en-us/library/hh849724.aspx)] コマンドレットを使用して最新バージョンのヘルプを取得し、指定した場所に保存します。 次に、インターネットに接続されていないサーバーの _-SourcePath_パラメーターを指定して**Update-ヘルプ**コマンドレットを使用して、選択した場所から更新されたヘルプを取得できます。 次の例は、ヘルプファイルをネットワークファイル共有に保存して、Skype for Business モジュールのヘルプをファイル共有から更新する方法を示しています。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    詳細については、「[更新可能なヘルプ](https://technet.microsoft.com/library/hh847735.aspx)」を参照してください。
    
    > [!NOTE]
    > PowerShell をリモートで使用している場合は、ファイアウォール経由の通信を許可する必要があります。 PowerShell のリモート処理で使用されるポートの詳細については、「 [Powershell リモート処理で使用](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)されるポートについて」を参照してください。
    

