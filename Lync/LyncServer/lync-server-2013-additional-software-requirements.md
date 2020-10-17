---
title: 'Lync Server 2013: 追加のソフトウェア要件'
description: 'Lync Server 2013: 追加のソフトウェア要件。'
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
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553043"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013 の追加ソフトウェア要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、サーバープラットフォームのハードウェアとオペレーティングシステムの要件に加えて、展開するサーバーに追加のソフトウェアをインストールする必要があります。

<div>


> [!NOTE]  
> Lync Server を実行しているサーバーのプラットフォーム要件の詳細については、「lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 のサーバーハードウェアプラットフォーム</A> 」および「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013 のサーバーおよびツールのオペレーティングシステムのサポート</A>」を参照してください。 クライアントコンピューターとデバイスのシステム要件の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">planning for clients and devices In Lync Server 2013</A> 」を参照してください。 管理ツールのソフトウェア要件の詳細については、「 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 の管理ツールのソフトウェア要件</A>」を参照してください。



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>すべての内部サーバーの役割に必要な追加ソフトウェア

このセクションでは、すべての内部サーバーの役割に必要なソフトウェアを一覧表示します。これは、エッジサーバーを除くすべての Lync Server サーバーの役割です。 エッジサーバーとエッジプールの要件については、このトピックで後述する「 **エッジサーバーの追加ソフトウェア**」を参考にしてください。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 を実行している各サーバーに、正しいリリースの Windows PowerShell 3.0 がインストールされている必要があります。 詳細については、「 [Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server には、すべての内部サーバーの役割に Microsoft .NET Framework 4.5 が必要です。また、Lync Server 管理ツールまたは Microsoft Lync Server 2013、計画ツールを実行するすべてのコンピューターで、Microsoft .NET Framework が必要です。 Lync server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。 これを手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 Framework をダウンロードしてください。 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Windows Server 2012 を実行しているサーバーに Microsoft .NET Framework 4.5 をインストールする

Lync Server 2013 および Windows Server 2012 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、1つの追加の手順を実行する必要があります。 .NET Framework 4.5 をインストールした後、サーバーマネージャーを使用して HTTP アクティブ化をインストールします。

**Windows Server 2012 に .NET 4.5 HTTP ライセンス認証をインストールするには**

1.  [ **スタート** ] メニューの [ **プログラム**] をクリックし、[ **管理ツール**] をクリックして、[ **サーバーマネージャー**] をクリックします。

2.  サーバーマネージャーの [ **機能の概要**] で、[ **機能の追加**] を選択します。

3.  [ **.Net Framework 4.5**] を展開します。

4.  まだ選択されていない場合は、[ **WCF アクティブ化** ] を選択します。 [ **HTTP アクティブ化**] を選択します。

5.  [ **次へ** ] をクリックし、画面の指示に従ってインストールを完了します。

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために Windows identity foundation をインストールする必要があります。 Windows Server 2008 R2 および Windows Server 2012 には、Windows 識別基盤をインストールするための異なる手順が必要です。 次の一覧から、サーバーオペレーティングシステムを選択します。

  - Windows Server 2008 R2 For Windows Server 2008 R2 コンピューターに既にインストールされているかどうかを確認するには、このチェックボックスをオンにします。 これを行うには、「**プログラムの追加と削除**」、「**インストール済みの更新プログラムの表示**」の順に移動して、WINDOWS **Identity Foundation (KB974405)****のエントリ**を確認します。 Windows Identity Foundation のインストールの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。

  - Windows server 2012 For Windows server 2012 では、 **サーバーマネージャー** を使用して Windows Identity Foundation をインストールします。 サーバーマネージャーの **役割と機能の追加ウィザード**で、[ **機能**] を選択します。 一覧から [ **Windows Identity Foundation 3.5** ] を選択します。 [ **次へ**] をクリックし、[ **インストール**] をクリックします。

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>すべてのフロントエンドサーバーおよび Standard Edition サーバーの追加ソフトウェア

また、すべてのフロントエンドサーバーと Standard Edition サーバーで、特定のモジュールを使用してインターネットインフォメーションサービス (IIS) を実行する必要があります。 また、会議、コールパークアプリケーション、アナウンス、または応答グループが展開されているすべてのフロントエンドサーバーおよび Standard Edition サーバーは、Windows Media フォーマットランタイムを実行する必要があります。

<div>

## <a name="internet-information-services-iis"></a>インターネット インフォメーション サービス (IIS)

フロントエンドサーバーおよび Standard Edition サーバーは、次のモジュールを使用してインターネットインフォメーションサービス (IIS) を実行する必要があります。

  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET 拡張機能

  - Internet Server API (ISAPI) 拡張機能

  - ISAPI フィルター

  - HTTP ロギング機能

  - ログ ツール

  - ・

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - 動的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS のインストール時に既定でインストールされます)

  - クライアント証明書マッピング認証

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media フォーマットランタイムと Windows デスクトップでの作業

**Windows デスクトップ環境** 会議を展開するすべてのフロントエンドサーバーおよび Standard Edition サーバーには、windows Media フォーマットランタイムがインストールされている必要があります。これは、windows Server 2012 を除き、windows デスクトップ環境の一部としてインストールされます。 Windows Server 2012 には、Microsoft Media Foundation が必要です。 コール パーク、アナウンス、応答グループの各アプリケーションがアナウンスと音楽を再生する Windows Media オーディオ (.wma) ファイルを実行するには、Windows Media フォーマット ランタイムが必要です。

Lync Server 2013 をインストールする前に、Windows デスクトップ環境をインストールすることをお勧めします。 Lync Server 2013 がサーバー上でこのソフトウェアを見つけられない場合は、インストールを求めるメッセージが表示され、インストールを完了するためにサーバーを再起動する必要があります。

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Windows Server 2012 上で実行されているフロントエンドサーバーおよび Standard Edition サーバーの追加ソフトウェア

フロントエンドサーバーには、Windows Server 2012 に既定でインストールされていない .NET 3.5 が必要です。 インストールするには、Windows Server 2012 インストールメディアをドライブ D に挿入し、次のように入力します。

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Windows Server 2012 を実行しているサーバーへの .NET 3.5 のインストールの詳細については、「」の「Microsoft .NET Framework 3.5 の展開に関する考慮事項」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=275032> 。

</div>

<div>

## <a name="additional-software-for-directors"></a>ディレクターの追加ソフトウェア

ディレクターは、次のモジュールを使用してインターネットインフォメーションサービス (IIS) を実行する必要があります。

  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET 拡張機能

  - Internet Server API (ISAPI) 拡張機能

  - ISAPI フィルター

  - HTTP ロギング機能

  - ログ ツール

  - ・

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS のインストール時に既定でインストールされます)

  - クライアント証明書マッピング認証

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>常設チャットフロントエンドサーバー用の追加ソフトウェア

常設チャットフロントエンドサーバーは、Windows Server のコンポーネントであるメッセージキュー (MSMQ とも呼ばれます) を実行する必要があります。

MSMQ を有効にする方法については、 [ここをクリックしてください。](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>エッジサーバーの追加ソフトウェア

エッジサーバーには、次のソフトウェアが必要です。

  - Lync Server 2013 を実行している各サーバーに、正しいリリースの Windows PowerShell 3.0 がインストールされている必要があります。 詳細については、「 [Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

  - Lync Server には Microsoft .NET Framework 4.5 が必要です。 Windows Server 2008 R2 にインストールされている Lync Server 2013 では、Lync 2013 Server をインストールする前に、サーバーに Microsoft .NET Framework 4.5 の64ビットエディションを手動でインストールする必要があります。 これを手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 Framework をダウンロードしてください。 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために Windows identity foundation をインストールする必要があります。 Windows Server 2008 R2 および Windows Server 2012 には、Windows 識別基盤をインストールするための異なる手順が必要です。 次の一覧から、サーバーオペレーティングシステムを選択します。
    
      - Windows Server 2008 R2 For Windows Server 2008 R2 コンピューターに既にインストールされているかどうかを確認するには、このチェックボックスをオンにします。 これを行うには、「**プログラムの追加と削除**」、「**インストール済みの更新プログラムの表示**」の順に移動して、WINDOWS **Identity Foundation (KB974405)****のエントリ**を確認します。 Windows Identity Foundation のインストールの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。
    
      - Windows server 2012 For Windows server 2012 では、 **サーバーマネージャー** を使用して Windows Identity Foundation をインストールします。 サーバーマネージャーの **役割と機能の追加ウィザード**で、[ **機能**] を選択します。 一覧から [ **Windows Identity Foundation 3.5** ] を選択します。 [ **次へ**] をクリックし、[ **インストール**] をクリックします。

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>複数層ソケット プロバイダーをメディア サーバーにインストールしないこと

任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバーに、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他の Winsock 階層サービスプロバイダ (LSP) ソフトウェアをインストールしないでください。 このソフトウェアをインストールすると、メディアトラフィックのパフォーマンスが低下する可能性があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の管理ツールソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

