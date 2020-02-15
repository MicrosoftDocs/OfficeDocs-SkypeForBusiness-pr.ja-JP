---
title: Skype for Business Server 管理シェル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 管理シェルには、サーバーの管理および管理用のコマンドラインインターフェイスが用意されています。 これは Windows PowerShell に基づいて構築されており、Skype および従来の Lync server 製品に固有の管理コマンドレットおよび管理コマンドレットの包括的なセットが含まれています。
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044259"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル
 
Skype for Business Server 管理シェルには、サーバーの管理および管理用のコマンドラインインターフェイスが用意されています。 これは Windows PowerShell に基づいて構築されており、Skype および従来の Lync server 製品に固有の管理コマンドレットおよび管理コマンドレットの包括的なセットが含まれています。
  
Windows PowerShell を使用すると、コマンドラインから Microsoft アプリケーションを管理できます。 Windows PowerShell にはコマンドライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれます。 Windows PowerShell は、最初は2006でリリースされた Windows オペレーティングシステム用のダウンロード可能なリリースとして導入され、Microsoft Exchange Server 2007 を管理するためのコマンドラインインターフェイスとして組み込まれていました。 Lync および Skype サーバーを含む、Lync Server 2010 を含む、ほとんどの Microsoft サーバー製品に組み込まれています。 Skype for Business Server 管理シェルでは、700以上の Lync および Skype 固有のコマンドレットを使用できます。
  
> [!NOTE]
> Skype for Business のコマンドレットリファレンスが docs.microsoft.com に移動されました。 以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。 これで、GitHub を通じてコミュニティの投稿に使用できるようになるコンテンツが公開されました。 投稿に興味はありますか? ここでは、リポジトリ内の README を確認してください。[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for business Server には、管理者が Skype for Business Server 管理シェルを使用して Skype for business Server を管理できるようにする、700を超えるコマンドレットが付属しています。 コマンドラインからコマンドレットのヘルプを直接取得するには、次のようなコマンドを入力します。
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

前述のコマンドは、**New-CsVoicePolicy** コマンドレットで使用できるすべてのヘルプを取得します。 別のコマンドレットのヘルプを表示するには、**New-CsVoicePolicy** を、ヘルプを取得したいコマンドレットの名前に置き換えます。
  
Skype for Business Server の管理に使用できるコマンドレットの完全な一覧を取得するには、シェルコマンドプロンプトで次のように入力します。 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Skype for Business Server の Windows PowerShell について知っておくべき事柄:
  
- Skype for Business Server のコマンドレットを実行するには、Skype for business Server 管理シェルを開きます。
    
    > [!CAUTION]
    > Skype for Business Server 管理シェルではなく、Windows PowerShell ウィンドウを開くと、既定では Skype コマンドレットを実行できない場合があります。 Windows PowerShell で Skype for Business Server のコマンドレットを実行するには、まず Windows PowerShell コマンドプロンプトで次のように入力します。 >`Import-Module SkypeforBusiness`
  
- Skype for Business Server 管理シェルは、すべての Skype for Business Server Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされます。
    
- Skype for Business Server 管理シェルのヘルプコンテンツを更新するには、 [help](https://technet.microsoft.com/library/hh849720.aspx)コマンドレットを実行します。 Help コマンドレットは、Skype for Business コマンドレットの更新を含む、コンピューターにインストールされているすべてのモジュールで利用可能な最新のヘルプファイルをダウンロードしてインストールします。
    
    既定では、 **Help**コマンドレットは、Skype For business Server にインストールされているすべてのモジュールを更新します。 特定のモジュールのみを更新する場合は、 _Module_パラメーターを使用してコマンドレットのスコープを制限できます。 次の例では、Skype for Business モジュールのみが更新されます。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    インターネットに接続されていないサーバーでヘルプを更新する必要がある場合[は、help コマンドレット](https://technet.microsoft.com/library/hh849724.aspx)を使用して、最新バージョンのヘルプを取得し、指定した場所に保存することができます。 その後、インターネットに接続されていないサーバーで _-SourcePath_パラメーターを指定して、 **help**コマンドレットを使用して、選択した場所から更新されたヘルプを取得できます。 次の例は、ヘルプファイルをネットワークファイル共有に保存した後、Skype for Business モジュールのヘルプをファイル共有から更新する方法を示しています。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    詳細については、「[更新可能なヘルプ](https://technet.microsoft.com/library/hh847735.aspx)」を参照してください。
    
    > [!NOTE]
    > PowerShell をリモートで使用している場合は、ファイアウォール経由の通信を許可する必要があります。 PowerShell リモート処理で使用されるポートの詳細については、「 [Powershell リモート処理で使用](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)されるポート」を参照してください。
    

