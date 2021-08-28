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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: サーバー Skype for Business Server管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Windows PowerShellおよび従来の Lync サーバー製品に固有の管理コマンドレットと管理コマンドレットのSkype組み込まれています。
ms.openlocfilehash: dbff67d52d616d55d8e183ffab91126f8546f1b1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609294"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル
 
サーバー Skype for Business Server管理シェルは、サーバーの管理と管理のためのコマンド ライン インターフェイスを提供します。 このコマンドレットは、Windows PowerShellおよび従来の Lync サーバー製品に固有の管理コマンドレットと管理コマンドレットのSkype組み込まれています。
  
Windows PowerShellコマンド ラインから Microsoft アプリケーションを管理できます。 Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。 Windows PowerShellは、2006 年後半に Windows オペレーティング システムのダウンロード可能なリリースとして初めて導入され、Microsoft Exchange Server 2007 の管理性を確保するためのコマンド ライン インターフェイスとして組み込まれた。 これは、Lync Server 2010 で始まる Lync および Skypeサーバーなど、ほとんどの Microsoft Server 製品に組み込まれています。 700 を超える Lync および Skypeのコマンドレットは、Skype for Business Server管理シェルで使用できます。
  
> [!NOTE]
> Skype for Businessコマンドレット参照は、このコマンドレットに docs.microsoft.com。 以下のリンクをクリックすると、新しいページ docs.microsoft.com されます。 コンテンツはオープンソースで、コミュニティへの投稿に利用GitHub。 貢献に興味がありますか? repo の README を確認してください。 [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server 700 以上のコマンドレットが含め、管理者は管理シェルを使用してSkype for Business ServerをSkype for Business Serverできます。 次のようなコマンドを入力すると、コマンド ラインからコマンドレットのヘルプを直接取得できます。
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。
  
データベースの管理に使用できるコマンドレットの完全なSkype for Business Server取得するには、シェル コマンド プロンプトで次のコマンドを入力します。 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



次に示す、Windows PowerShellのSkype for Business Server。
  
- このコマンドレットを実行Skype for Business Server、管理シェルSkype for Business Server開きます。
    
    > [!CAUTION]
    > 管理シェルではなく Windows PowerShell ウィンドウを開Skype for Business Server既定では、このコマンドレットを実行Skypeがあります。 コマンドレットを Skype for Business Serverから実行するには、Windows PowerShellコマンド プロンプトで最初に次Windows PowerShell入力します>`Import-Module SkypeforBusiness`
  
- Skype for Business Server管理シェルは、すべてのフロントエンド サーバーまたはSkype for Business Server Enterprise EditionサーバーにStandard Editionされます。
    
- Update-Help コマンドレットを実行Skype for Business Server管理シェル のヘルプ コンテンツ[を更新](/powershell/module/microsoft.powershell.core/update-help)できます。 このUpdate-Helpは、コンピューターにインストールされているすべてのモジュールで利用可能な最新のヘルプ ファイルをダウンロードし、インストールします 。このSkype for Businessします。
    
    既定では **、Update-Help コマンドレット** は、コンピューターにインストールされているすべてのモジュールを更新Skype for Business Server。 特定のモジュールのみを更新する場合は _、Module_ パラメーターを使用してコマンドレットのスコープを制限できます。 次の使用例は、モジュールのSkype for Businessします。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    インターネットに接続されていないサーバーでヘルプを更新する必要がある場合は [、Save-Help](/powershell/module/microsoft.powershell.core/save-help) コマンドレットを使用して、ヘルプの最新バージョンを取得し、指定した場所に保存できます。 その後 **、Update-Help** コマンドレットを使用して、インターネットに接続されていないサーバー上の _-SourcePath_ パラメーターを使用して、選択した場所から更新されたヘルプを取得できます。 次の例は、ヘルプ ファイルをネットワーク ファイル共有に保存し、ファイル共有から Skype for Businessモジュールのヘルプを更新する方法を示しています。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    詳細については、「更新可能なヘルプ [について」を参照してください](/powershell/module/microsoft.powershell.core/about/about_updatable_help)。
    
    > [!NOTE]
    > PowerShell をリモートで使用している場合は、ファイアウォール経由の通信を許可する必要があります。 PowerShell リモート処理で使用されるポートの詳細については、「PowerShell リモート処理で使用する [ポート」を参照してください](/archive/blogs/christwe/what-port-does-powershell-remoting-use)。
