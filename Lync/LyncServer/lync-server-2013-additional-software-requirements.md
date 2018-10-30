---
title: 'Lync Server 2013: 追加ソフトウェア要件'
TOCTitle: 追加ソフトウェア要件
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48272740
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の追加ソフトウェア要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、サーバー プラットフォーム用のハードウェアおよびオペレーティング システムの要件のほか、展開するサーバーに対して追加ソフトウェアをインストールする必要があります。

> [!NOTE]
> Lync Server を実行するサーバーのプラットフォームの要件の詳細については、「<a href="lync-server-2013-server-hardware-platforms.md">Lync Server 2013　用のサーバー ハードウェア プラットフォーム</a>」および「<a href="lync-server-2013-server-and-tools-operating-system-support.md">Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート</a>」を参照してください。クライアント コンピューターおよびデバイスのシステム要件の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 のクライアントとデバイスの計画</a>」を参照してください。管理ツールのソフトウェア要件の詳細については、「<a href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 の管理ツールのソフトウェア要件</a>」を参照してください。


## すべての内部サーバーの役割に必要な追加ソフトウェア

このセクションでは、すべての内部サーバーの役割 (エッジ サーバーを除くすべて Lync Server のサーバーの役割) で必要なソフトウェアを示します。エッジ サーバーおよびエッジ プールに関する要件は、このトピックの後半の「**エッジ サーバーの追加のソフトウェア**」に示されています。

## Windows PowerShell 3.0

Lync Server 2013 を実行するそれぞれのサーバーには、 Windows PowerShell 3.0 の正しいリリースがインストールされている必要があります。詳細については、「[Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

## Microsoft .NET Framework 4.5

Lync Server では、すべての内部サーバーの役割、およびユーザーが Lync Server 管理ツールまたはMicrosoft Lync Server 2013、計画ツールを実行するすべてのコンピューターで Microsoft .NET Framework 4.5 が必要です。Lync Server 2013 の場合は、Lync Server 2013 をインストールする前に、64 ビット版の Microsoft .NET Framework 4.5 をサーバーに手動でインストールする必要があります。Microsoft .NET Framework 4.5 の 64 ビット版を手動でインストールするには、Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529)) から Microsoft .NET 4.5 Framework をダウンロードします。

## Windows Server 2012 を実行するサーバーへの Microsoft .NET Framework 4.5 のインストール

Lync Server 2013 および Windows Server 2012 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールするときは、実行する必要のある追加手順が 1 つあります。.NET Framework 4.5 をインストールした後、サーバー マネージャーを使用して HTTP アクティブ化をインストールします。

**.NET 4.5 HTTP アクティブ化を Windows Server 2012 にインストールするには**

1.  \[**スタート**\] メニューから、\[**プログラム**\]、\[**管理ツール**\]、\[**サーバー マネージャー**\] の順にクリックします。

2.  サーバー マネージャーで、\[**機能の概要**\] の \[**機能の追加**\] を選択します。

3.  \[**.NET Framework 4.5**\] を展開します。

4.  \[**WCF アクティブ化**\] がまだ選択されていない場合は選択します。次に、\[**HTTP アクティブ化**\] を選択します。

5.  \[**次へ**\] をクリックし、表示される指示に従ってインストールを完了します。

## Windows Identity Foundation

Lync Server 2013 の **Windows Identity Foundation** でサーバー間認証シナリオをサポートするには、Windows Identity Foundation をインストールする必要があります。 Windows Server 2008 R2 と Windows Server 2012 では、Windows Identify Foundation をインストールするために必要な手順が異なります。以下のリストからサーバーのオペレーティング システムを選択してください。

  - Windows Server 2008 R2    Windows Server 2008 R2 がインストールされているか確認する必要があります。これを行うには、\[**プログラムの追加と削除**\] の \[**インストールされている更新プログラムを表示**\] へ移動し、\[**Windows**\] の下で **Windows Identity Foundation (KB974405)** を探してください。Windows Identity Foundation のインストールの詳細については、 <http://go.microsoft.com/fwlink/?linkid=204657> を参照してください。

  - Windows Server 2012    Windows Server 2012 では、\[**サーバー マネージャー**\] を使用して Windows Identity Foundation をインストールします。\[サーバー マネージャー\] の \[**役割と機能の追加ウィザード**\] で、\[**機能**\] を選択します。リストから \[**Windows Identity Foundation 3.5**\] を選択します。\[**次へ**\]、\[**インストール**\] の順にクリックします。

## すべてのフロントエンド サーバーおよび Standard Edition サーバーの追加ソフトウェア

すべてのフロントエンド サーバーと Standard Edition サーバーで、 インターネット インフォメーション サービス (IIS) と特定のモジュールも実行する必要があります。また、会議、 コール パーク アプリケーション、アナウンス、または応答グループを展開するすべてのフロントエンド サーバーと Standard Edition サーバーで、Windows Media フォーマット ランタイムを実行する必要があります。

## インターネット インフォメーション サービス (IIS)

フロントエンド サーバーと Standard Edition サーバーは、 インターネット インフォメーション サービス (IIS) を以下のモジュールと共に実行する必要があります。

  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET 拡張機能

  - Internet Server API (ISAPI) 拡張機能

  - ISAPI フィルター

  - HTTP ロギング機能

  - ログ ツール

  - 追跡

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - 動的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS のインストール時に既定でインストールされます)

  - クライアント証明書マッピング認証

## Windows Media フォーマット ランタイムおよび Windows デスクトップ エクスペリエンス

**Windows デスクトップ エクスペリエンス**会議を展開する予定のすべてのフロントエンド サーバーと Standard Edition サーバーで、Windows Media フォーマット ランタイムをインストールする必要があります。Windows Media フォーマット ランタイムは、 Windows Server 2012 を除き、Windows デスクトップ エクスペリエンスの一貫としてインストールされます。 Windows Server 2012 では Microsoft Media Foundation が必要です。 コール パーク、アナウンス、応答グループの各アプリケーションがアナウンスと音楽を再生する Windows Media オーディオ (.wma) ファイルを実行するには、Windows Media フォーマット ランタイムが必要です。

Windows Media デスクトップ エクスペリエンスは、 Lync Server 2013 をインストールする前にインストールすることをお勧めします。このソフトウェアが Lync Server 2013 によってサーバーから検出されない場合は、このソフトウェアのインストールを指示するメッセージが表示されます。このメッセージが表示されたら、サーバーを再起動してインストールを完了する必要があります。

## Windows Server 2012 上で実行するフロントエンド サーバーおよび Standard Edition サーバーの追加ソフトウェア

フロント エンド サーバーでは .NET 3.5 が必要ですが、これは既定では Windows Server 2012 にインストールされません。インストールするには、Windows Server 2012 のインストール メディアをドライブ D に入れて、次のコマンドを入力します。

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Windows Server 2012 を実行するサーバーへの .NET 3.5 のインストールの詳細については、「Microsoft .NET Framework 3.5 展開に関する考慮事項」( <http://go.microsoft.com/fwlink/?linkid=275032>) を参照してください。

## ディレクターの追加ソフトウェア

ディレクターは、 インターネット インフォメーション サービス (IIS) を以下のモジュールと共に実行する必要があります。

  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET 拡張機能

  - Internet Server API (ISAPI) 拡張機能

  - ISAPI フィルター

  - HTTP ロギング機能

  - ログ ツール

  - 追跡

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS のインストール時に既定でインストールされます)

  - クライアント証明書マッピング認証

## 常設チャット フロントエンド サーバーの追加ソフトウェア

常設チャット フロントエンド サーバーは、Windows Server のコンポーネントであるメッセージ キュー (MSMQ とも呼ばれます) を実行する必要があります。

MSMQ の有効化の詳細については、[ここをクリック](http://technet.microsoft.com/ja-jp/library/cc771474.aspx)してください。

## エッジ サーバーの追加のソフトウェア

エッジ サーバーでは、以下のソフトウェアが必要です。

  - Lync Server 2013 を実行するそれぞれのサーバーには、 Windows PowerShell 3.0 の正しいリリースがインストールされている必要があります。詳細については、「[Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

  - Lync Server には Microsoft .NET Framework 4.5 が必要です。 Windows Server 2008 R2 に Lync Server 2013 をインストールする場合、Microsoft .NET Framework 4.5 の 64 ビット版をサーバーに手動でインストールしてから Lync Server 2013 をインストールする必要があります。Microsoft .NET Framework 4.5 の 64 ビット版を手動でインストールするには、Microsoft ダウンロード センター ( <http://go.microsoft.com/fwlink/?linkid=268529>) から Microsoft .NET 4.5 Framework をダウンロードします。

  - Lync Server 2013 の **Windows Identity Foundation** でサーバー間認証シナリオをサポートするには、Windows Identity Foundation をインストールする必要があります。 Windows Server 2008 R2 と Windows Server 2012 では、Windows Identify Foundation をインストールするために必要な手順が異なります。以下のリストからサーバーのオペレーティング システムを選択してください。
    
      - Windows Server 2008 R2    Windows Server 2008 R2 がインストールされているか確認する必要があります。これを行うには、\[**プログラムの追加と削除**\] の \[**インストールされている更新プログラムを表示**\] へ移動し、\[**Windows**\] の下で **Windows Identity Foundation (KB974405)** を探してください。Windows Identity Foundation のインストールの詳細については、 <http://go.microsoft.com/fwlink/?linkid=204657> を参照してください。
    
      - Windows Server 2012    Windows Server 2012 では、\[**サーバー マネージャー**\] を使用して Windows Identity Foundation をインストールします。\[サーバー マネージャー\] の \[**役割と機能の追加ウィザード**\] で、\[**機能**\] を選択します。リストから \[**Windows Identity Foundation 3.5**\] を選択します。\[**次へ**\]、\[**インストール**\] の順にクリックします。

## 複数層ソケット プロバイダーをメディア サーバーにインストールしないこと

Microsoft Internet Security and Acceleration (ISA) Server クライアント ソフトウェアまたは他の Winsock Layered Service Providers (LSP) ソフトウェアを、フロントエンド サーバーまたはスタンドアロン仲介サーバーにインストールしないでください。このソフトウェアをインストールすると、メディア トラフィックのパフォーマンスの低下を招く可能性があります。

## 関連項目

#### 概念

[Lync Server 2013 の管理ツールのソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)

