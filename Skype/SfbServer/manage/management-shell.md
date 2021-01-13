---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Windows PowerShell上に構築され、Skype および従来の Lync サーバー製品に固有の管理および管理コマンドレットの包括的なセットが含まれています。
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816537"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル
 
Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Windows PowerShell上に構築され、Skype および従来の Lync サーバー製品に固有の管理および管理コマンドレットの包括的なセットが含まれています。
  
Windows PowerShellコマンド ラインから Microsoft アプリケーションを管理できます。 Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。 Windows PowerShellは、2006 年後半に Windows オペレーティング システムのダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理性を確保するためのコマンド ライン インターフェイスとして組み込まれたものになります。 これは、Lync Server 2010 で始まる Lync サーバーや Skype サーバーを含む、ほとんどの Microsoft Server 製品に組み込まれています。 Skype for Business Server 管理シェルには、700 を超える Lync および Skype 固有のコマンドレットを使用できます。
  
> [!NOTE]
> Skype for Business コマンドレット リファレンスは、docs.microsoft.com。 以下のリンクをクリックすると、新しいページdocs.microsoft.comされます。 コンテンツはオープン ソースとして公開され、GitHub を通じてコミュニティへの投稿に利用できます。 関心がある場合 以下のレポで README を確認してください。 [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server には、管理者が Skype for Business Server 管理シェルを使用して Skype for Business Server を管理できる 700 を超えるコマンドレットが組み込されています。 次のようなコマンドを入力すると、コマンド ラインから直接コマンドレットのヘルプを取得できます。
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。 別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。
  
Skype for Business Server の管理に使用できるコマンドレットの完全な一覧を取得するには、シェル コマンド プロンプトで次を入力します。 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Skype for Business Server のWindows PowerShellについて知る必要があります。
  
- Skype for Business Server コマンドレットを実行するには、Skype for Business Server 管理シェルを開きます。
    
    > [!CAUTION]
    > Skype for Business Server 管理シェルWindows PowerShell新しいウィンドウを開いた場合、既定では Skype コマンドレットを実行できない場合があります。 Skype for Business Server コマンドレットを Windows PowerShell から実行するには、最初に次のコマンド プロンプトで次Windows PowerShell入力します。>  `Import-Module SkypeforBusiness`
  
- Skype for Business Server 管理シェルは、すべての Skype for Business Server Enterprise Edition フロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされます。
    
- Skype for Business Server 管理シェル のヘルプ コンテンツを更新するには [、Update-Help コマンドレットを実行](https://technet.microsoft.com/library/hh849720.aspx) します。 次Update-Helpコマンドレットは、Skype for Business コマンドレットの更新プログラムを含め、コンピューターにインストールされているモジュールのすべてで使用可能な最新のヘルプ ファイルをダウンロードしてインストールします。
    
    既定では **、Update-Help** コマンドレットは Skype for Business Server にインストールされているモジュールを更新します。 特定のモジュールのみを更新する場合は _、Module_ パラメーターを使用してコマンドレットのスコープを制限できます。 次の例では、Skype for Business モジュールのみを更新します。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は [、Save-Help](https://technet.microsoft.com/library/hh849724.aspx) コマンドレットを使用してヘルプの最新バージョンを取得し、指定した場所に保存できます。 その後、インターネットに接続されていないサーバーで **Update-Help** コマンドレットを _-SourcePath_ パラメーターと共に使用して、選択した場所から更新されたヘルプを取得できます。 次の例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有から Skype for Business モジュールのヘルプを更新する方法を示しています。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    詳細については、「更新可能なヘルプ [について」を参照してください](https://technet.microsoft.com/library/hh847735.aspx)。
    
    > [!NOTE]
    > リモートで PowerShell を使用している場合は、ファイアウォール経由の通信を許可する必要があります。 PowerShell リモート処理で使用されるポートの詳細については [、「PowerShell リモート処理で使用するポート」を参照してください](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。
    

