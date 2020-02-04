---
title: 'Lync Server 2013: 追加ソフトウェア要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013 の追加ソフトウェア要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-08_

Lync Server 2013 では、サーバープラットフォームのハードウェアとオペレーティングシステムの要件に加えて、展開するサーバーに追加のソフトウェアをインストールする必要があります。

<div>


> [!NOTE]  
> Lync Server を実行しているサーバーのプラットフォーム要件の詳細については、「lync <A href="lync-server-2013-server-hardware-platforms.md">server 2013 のサーバーハードウェアプラットフォーム</A>」および「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013 のサーバーとツールのオペレーティングシステムのサポート</A>」を参照してください。 クライアントコンピューターとデバイスのシステム要件の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 でのクライアントとデバイスの計画</A>」を参照してください。 管理ツールのソフトウェア要件の詳細については、「 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 での管理ツールのソフトウェア要件</A>」を参照してください。



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>すべての内部サーバーの役割に必要なその他のソフトウェア

このセクションでは、すべての内部サーバーロールで必要なソフトウェアの一覧を示します。これは、エッジサーバーを除くすべての Lync Server server ロールです。 エッジサーバーとエッジプールの要件については、このトピックの「**エッジサーバー向けの追加ソフトウェア**」で説明しています。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 を実行している各サーバーには、正しいバージョンの Windows PowerShell 3.0 がインストールされている必要があります。 詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server を使用するには、社内のすべてのサーバーの役割、および Lync Server 管理ツールまたは Microsoft Lync Server 2013、計画ツールを実行するすべてのコンピューターで Microsoft .NET Framework 4.5 が必要です。 Lync Server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。 手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 フレームワークをダウンロードしてください。[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Windows Server 2012 を実行しているサーバーに Microsoft .NET Framework 4.5 をインストールする

Lync Server 2013 と Windows Server 2012 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、追加の手順を1つ実行する必要があります。 .NET Framework 4.5 がインストールされたら、サーバーマネージャーを使用して、HTTP アクティブ化をインストールします。

**Windows Server 2012 で .NET 4.5 HTTP ライセンス認証をインストールするには**

1.  [**スタート**] メニューで、[**プログラム**]、[**管理ツール**]、[**サーバーマネージャー**] の順にクリックします。

2.  サーバーマネージャーの [**機能の概要**] で、[**機能の追加**] を選択します。

3.  **.Net Framework 4.5**を展開します。

4.  まだ選択されていない場合は、[ **WCF ライセンス認証**] を選択します。 次に、[ **HTTP ライセンス認証**] を選択します。

5.  [**次へ**] をクリックし、画面の指示に従ってインストールを完了します。

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために、Windows id ファンデーションをインストールする必要があります。 Windows Server 2008 R2 および Windows Server 2012 では、Windows Id 基盤をインストールするために異なる手順が必要になります。 次の一覧からサーバーのオペレーティングシステムを選択します。

  - Windows server 2008 R2 For Windows Server 2008 R2 では、既にコンピューターにインストールされているかどうかを確認します。 これを行うには、「**プログラムの追加と削除**」、「**インストールされている更新プログラムを表示**」の各項目にアクセスして、「 **windows** **id ファンデーション (KB974405)**」を参照してください。 Windows Id Foundation のインストールの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)ては、を参照してください。

  - Windows server 2012 For Windows Server 2012 では、**サーバーマネージャー**を使って Windows Identity Foundation をインストールします。 サーバーマネージャーの**役割と機能の追加ウィザード**で、[**機能**] を選択します。 一覧から [ **Windows Id Foundation 3.5** ] を選びます。 [**次へ**] をクリックし、[**インストール**] をクリックします。

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>すべてのフロントエンドサーバーおよび標準エディションサーバー向けの追加ソフトウェア

すべてのフロントエンドサーバーと Standard Edition サーバーでは、特定のモジュールでインターネットインフォメーションサービス (IIS) を実行する必要もあります。 さらに、会議、コールパークアプリケーション、お知らせ、または応答グループが展開されているすべてのフロントエンドサーバーおよび標準エディションサーバーは、Windows Media Format Runtime を実行している必要があります。

<div>

## <a name="internet-information-services-iis"></a>インターネット インフォメーション サービス (IIS)

フロントエンドサーバーと Standard Edition サーバーでは、次のモジュールを使用して、インターネットインフォメーションサービス (IIS) を実行する必要があります。

  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET の拡張性

  - Internet Server API (ISAPI) の拡張機能

  - ISAPI フィルター

  - HTTP ログ

  - ログ ツール

  - トレース

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - 動的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS がインストールされると、既定でインストールされます。)

  - クライアント証明書マッピング認証

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime と Windows デスクトップエクスペリエンス

**Windows デスクトップエクスペリエンス**会議を展開するすべてのフロントエンドサーバーおよび標準エディションサーバーには、windows デスクトップエクスペリエンスの一部としてインストールされている windows Server 2012 以外の Windows Media Format ランタイムがインストールされている必要があります。 Windows Server 2012 には Microsoft メディアファンデーションが必要です。 Windows Media 形式ランタイムは、コールパーク、アナウンスメント、および応答グループアプリケーションがお知らせや音楽を再生するために、Windows Media オーディオ (.wma) ファイルを実行するために必要です。

Lync Server 2013 をインストールする前に、Windows デスクトップエクスペリエンスをインストールすることをお勧めします。 Lync Server 2013 でサーバー上にこのソフトウェアが見つからない場合は、インストールするように求められます。その後、インストールを完了するには、サーバーを再起動する必要があります。

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Windows Server 2012 で実行されているフロントエンドサーバーおよび標準エディションサーバー向けの追加ソフトウェア

フロントエンドサーバーには、Windows Server 2012 に既定でインストールされていない .NET 3.5 が必要です。 インストールするには、Windows Server 2012 インストールメディアを D ドライブに挿入し、次のように入力します。

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Windows Server 2012 を実行しているサーバーへの .NET 3.5 のインストールの詳細については、「 <https://go.microsoft.com/fwlink/p/?linkid=275032>Microsoft .net Framework 3.5 展開に関する考慮事項」を参照してください。

</div>

<div>

## <a name="additional-software-for-directors"></a>ディレクター向けのその他のソフトウェア

ディレクターは、次のモジュールを使用して、インターネットインフォメーションサービス (IIS) を実行している必要があります。

  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET の拡張性

  - Internet Server API (ISAPI) の拡張機能

  - ISAPI フィルター

  - HTTP ログ

  - ログ ツール

  - トレース

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS がインストールされると、既定でインストールされます。)

  - クライアント証明書マッピング認証

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>常設チャットフロントエンドサーバー向けの追加ソフトウェア

常設チャットフロントエンドサーバーでは、Windows Server のコンポーネントであるメッセージキュー (MSMQ とも呼ばれます) を実行する必要があります。

MSMQ を有効にする方法については、ここをクリックして[ください。](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>エッジサーバー向けの追加ソフトウェア

エッジサーバーには、次のソフトウェアが必要です。

  - Lync Server 2013 を実行している各サーバーには、正しいバージョンの Windows PowerShell 3.0 がインストールされている必要があります。 詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

  - Lync Server には Microsoft .NET Framework 4.5 が必要です。 Windows Server 2008 R2 にインストールされている Lync Server 2013 の場合、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。 手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 フレームワークをダウンロードしてください。[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために、Windows id ファンデーションをインストールする必要があります。 Windows Server 2008 R2 および Windows Server 2012 では、Windows Id 基盤をインストールするために異なる手順が必要になります。 次の一覧からサーバーのオペレーティングシステムを選択します。
    
      - Windows server 2008 R2 For Windows Server 2008 R2 では、既にコンピューターにインストールされているかどうかを確認します。 これを行うには、「**プログラムの追加と削除**」、「**インストールされている更新プログラムを表示**」の各項目にアクセスして、「 **windows** **id ファンデーション (KB974405)**」を参照してください。 Windows Id Foundation のインストールの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)ては、を参照してください。
    
      - Windows server 2012 For Windows Server 2012 では、**サーバーマネージャー**を使って Windows Identity Foundation をインストールします。 サーバーマネージャーの**役割と機能の追加ウィザード**で、[**機能**] を選択します。 一覧から [ **Windows Id Foundation 3.5** ] を選びます。 [**次へ**] をクリックし、[**インストール**] をクリックします。

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>階層ソケットプロバイダーをメディアサーバーにインストールしない

Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他の Winsock レイヤードサービスプロバイダ (LSP) ソフトウェアは、任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバーにインストールしないでください。 このソフトウェアをインストールすると、メディアトラフィックのパフォーマンスが低下する可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の管理ツールのソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

