---
title: Skype for Business Server 2015 の前提条件のインストール
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: については、サーバーとサーバーの役割がビジネス サーバー 2015 の Skype をインストールする前に構成する必要があります。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 の前提条件のインストール
 
**の概要:**サーバーとビジネス サーバー 2015 の Skype をインストールする前に構成する必要がありますサーバーの役割について説明します。 [マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からサーバー 2015 をビジネス用には、Skype の無料試用版をダウンロードします。
  
必須コンポーネントのインストールは、トポロジ内のサーバーごとに必要な役割と機能をインストールすることによって Windows のサーバーを設定するので構成されます。 要件は、サーバーをトポロジに満たす役割に基づいています。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。 8 のステップ 1 は、必須コンポーネントをインストールします。
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server をセットアップする

ビジネス サーバー 2015 の Skype では、インストールする前に Windows サーバー オペレーティング システムおよび前提条件の多くを必要です。 前提条件の計画に関する詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。 
  
> [!TIP]
> この手順では Windows Server 2012 R2 を使用します。別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。 
  
> [!IMPORTANT]
> 作業を開始する前に、Windows Server は、Windows Update を使用して最新の状態を確認します。 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
**前提条件のインストール**手順に関するビデオを見てください。
  
![ブラウザーがビデオをサポートしていません。Microsoft Silverlight、Adobe Flash Player、または Internet Explorer 9 をインストールしてください。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンド サーバーに必要な役割と機能をインストールする

1. サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。
    
2. [**開始する前に**] ページを読んで Windows Server への役割と機能のインストールについて理解を深めてから、[**次へ**] をクリックします。
    
3. [**役割ベースまたは機能ベースのインストール**] を選択し、[**次へ**] をクリックします。
    
4. サーバーにするビジネス サーバー 2015 年の Skype をインストールしてする [**次へ**] を選択します。
    
5. 役割として [**Web サーバー (IIS)**] を選択します。必要な機能に関するウィンドウが開いたら、[**機能の追加**] をクリックし、[**次へ**] をクリックします。
    
6. ビジネス サーバー 2015 の Skype を実行するサーバーでは、[サーバー 2015 のビジネスを展開するため、Skype の前にインストールするソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software)に記載されているソフトウェアの機能を確認します。 省略形の一覧を以下に示します。
    
   - .NET Framework の機能
    
   - WCF サービス
    
   - HTTP アクティブ化
    
    > [!NOTE]
    > HTTP アクティブ化には追加の機能が必要です。[HTTP アクティブ化] を選択したときに表示される警告ダイアログ ボックスで、[**機能の追加**] をクリックします。
  
   - メディアの基礎 (会議のために使用されるフロント エンド サーバーと Standard Edition のサーバーで必要な)。
    
   - リモート サーバー管理ツール
    
   - 役割管理ツール
    
   - AD DS 
    
   - AD LDS
    
   - Windows Identity Foundation 3.5
    
7. [**次へ**] をクリックして、ウィザードを続行します。
    
8. **Web サーバー (IIS) の役割**に関する注意を読み、[**次へ**] をクリックします。
    
9. **Web Server (IIS) の役割サービス**として次を選択します。
    
   - HTTP 共通機能
    
   - 既定のドキュメント
    
   - ディレクトリの参照
    
   - HTTP エラー
    
   - 静的コンテンツ
    
   - 状態と診断
    
   - HTTP ログ
    
   - ログ ツール
    
   - 追跡
    
   - パフォーマンス
    
   - 静的コンテンツ圧縮
    
   - 動的コンテンツ圧縮
    
   - セキュリティ
    
   - 要求のフィルタリング
    
   - クライアント証明書マッピング認証
    
   - Windows 認証
    
   - アプリケーション開発
    
   - .NET 拡張機能 3.5
    
   - .NET 拡張機能 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - ISAPI 拡張機能
    
   - ISAPI フィルター
    
   - 管理ツール
    
   - IIS 管理コンソール
    
   - IIS 管理スクリプトおよびツール
    
10. [**次へ**] をクリックして、ウィザードを続行します。
    
11. インストールに関する選択を見直し、すべての要件が選択されていることを確認して、[**インストール**] をクリックします。
    
    > [!CAUTION]
    > 既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。 サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。 ソース ファイルは sources\sxs ディレクトリにあります。 たとえば、Windows Server 2012 R2 メディアをドライブ D に挿入した場合は、パスを `d:\sources\sxs` に設定します。 > その方法は、Windows Update から最新の更新プログラムがあることが重要です。 インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。 
  
12. ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。
    
13. インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。
    
14. 使用する Skype ビジネス サーバーのコントロール パネルのこのサーバーの場合、Silverlight もインストールする必要があります。 Silverlight をインストールするには、 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)を参照してください。
    
前提条件となる各機能は、次の PowerShell コマンドを実行してインストールすることができます。 このコマンドがソース ファイルを探す順序に注意してください。 オンラインの場合、このコマンドは Windows Update にアクセスします。 一方、オフラインの場合は、このコマンドがソース ファイルにアクセスできるようにする必要があります。 PowerShell を使用して、役割と機能をインストールする詳細については、[インストールまたはアンインストールの役割、役割サービス、または機能](https://technet.microsoft.com/en-us/library/hh831809.aspx)と[インストール WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx)を参照してください。 前提条件となる機能のインストールが終わったら、PowerShell コマンドを使用した場合であっても、必ず Windows Update を再実行してください。
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。 サーバーの種類ごとに必要な正確な前提条件の詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。 
  

