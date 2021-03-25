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
description: Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Skype Windows PowerShell従来の Lync サーバー製品に固有の管理コマンドレットと管理コマンドレットの包括的なセットが含まれています。
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118586"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル
 
Skype for Business Server 管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Skype Windows PowerShell従来の Lync サーバー製品に固有の管理コマンドレットと管理コマンドレットの包括的なセットが含まれています。
  
Windows PowerShellコマンド ラインから Microsoft アプリケーションを管理できます。 Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。 Windows PowerShellは、2006 年後半に Windows オペレーティング システムのダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理性を確保するためのコマンド ライン インターフェイスとして組み込まれた。 これは、Lync Server 2010 で始まる Lync サーバーや Skype サーバーなど、ほとんどの Microsoft Server 製品に組み込まれています。 Skype for Business Server 管理シェルには、700 を超える Lync および Skype 固有のコマンドレットを使用できます。
  
> [!NOTE]
> Skype for Business コマンドレットの参照は、Skype for Business コマンドレットの docs.microsoft.com。 以下のリンクをクリックすると、新しいページ docs.microsoft.com されます。 このコンテンツはオープンソースで、GitHub を通じてコミュニティへの投稿に利用できます。 貢献に興味がありますか? repo の README を確認してください。 [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server には、管理者が Skype for Business Server 管理シェルを使用して Skype for Business Server を管理できる 700 を超えるコマンドレットが含されています。 次のようなコマンドを入力すると、コマンド ラインからコマンドレットのヘルプを直接取得できます。
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。 別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。
  
Skype for Business Server の管理に使用できるコマンドレットの完全な一覧を取得するには、シェル コマンド プロンプトで次を入力します。 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Skype for Business Server Windows PowerShellの詳細については、次の情報を参照してください。
  
- Skype for Business Server コマンドレットを実行するには、Skype for Business Server 管理シェルを開きます。
    
    > [!CAUTION]
    > Skype for Business Server 管理シェルWindows PowerShellウィンドウを開く場合、既定では Skype コマンドレットを実行できない場合があります。 Skype for Business Server コマンドレットを Windows PowerShell 内から実行するには、まず、次のコマンド プロンプトで次Windows PowerShell入力します>  `Import-Module SkypeforBusiness`
  
- Skype for Business Server Management Shell は、すべての Skype for Business Server Enterprise Edition フロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされます。
    
- Update-Help コマンドレットを実行すると、Skype for Business Server 管理シェルのヘルプ [コンテンツを更新](/powershell/module/microsoft.powershell.core/update-help) できます。 このUpdate-Helpは、Skype for Business コマンドレットの更新プログラムを含め、コンピューターにインストールされているモジュールすべてで利用可能な最新のヘルプ ファイルをダウンロードしてインストールします。
    
    既定では **、Update-Help コマンドレット** は、Skype for Business Server にインストールされているすべてのモジュールを更新します。 特定のモジュールのみを更新する場合は _、Module_ パラメーターを使用してコマンドレットのスコープを制限できます。 次の例では、Skype for Business モジュールのみを更新します。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は [、Save-Help](/powershell/module/microsoft.powershell.core/save-help) コマンドレットを使用して、ヘルプの最新バージョンを取得し、指定した場所に保存できます。 その後 **、Update-Help** コマンドレットを使用して、インターネットに接続されていないサーバー上の _-SourcePath_ パラメーターを使用して、選択した場所から更新されたヘルプを取得できます。 次の例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有から Skype for Business モジュールのヘルプを更新する方法を示しています。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    詳細については、「更新可能なヘルプ [について」を参照してください](/powershell/module/microsoft.powershell.core/about/about_updatable_help)。
    
    > [!NOTE]
    > PowerShell をリモートで使用している場合は、ファイアウォール経由の通信を許可する必要があります。 PowerShell リモート処理で使用されるポートの詳細については、「PowerShell リモート処理で使用する [ポート」を参照してください](/archive/blogs/christwe/what-port-does-powershell-remoting-use)。
