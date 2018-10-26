---
title: 'Lync Server 2013: Lync Server 2013 を実行するサーバーのシステム要件'
TOCTitle: Lync Server 2013 を実行するサーバーのシステム要件
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48272551
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 を実行するサーバーのシステム要件

 

_**トピックの最終更新日:** 2016-12-08_

> [!NOTE]
> ハードウェア要件の詳細については、「<a href="lync-server-2013-server-hardware-platforms.md">Lync Server 2013　用のサーバー ハードウェア プラットフォーム</a>」を参照してください。


Standard Edition と Enterprise Edition の各サーバーは、同じソフトウェア要件を共有しています。

Lync Server 2013 の Enterprise Edition を実行しているサーバーは、主要な組織展開として大規模な組織を対象としています。Enterprise Edition サーバーは、1 プールにつき、約 80,000 の所属ユーザーにまで対応できるように設計されています。 Lync Server 2013 Standard Edition を実行しているサーバーは、より小規模な組織および主要な組織展開から離れたリモートの場所を対象としています。 Standard Edition サーバーの 1 つのペアで、最大 5,000 ユーザーをサポートできます。Standard Edition サーバーと Enterprise Edition サーバーの違いの詳細については、「[Lync Server 2013 の展開の概要](lync-server-2013-deployment-overview.md)」を参照してください。

## オペレーティング システムのインストール


> [!IMPORTANT]
> Lync Server 2013 は、64 ビットのハードウェアおよび 64 ビット版の Windows Server オペレーティング システムを必要とする 64 ビット版のみが用意されています。32 ビット版の Lync Server 2013 は、今回のリリースでは用意されていません。



Standard Edition および Enterprise Edition のサーバーでは、次のどちらでも使用できます。

  - Windows Server 2008 R2 SP1 または最新のサービス パック

  - Windows Server 2012

  - Windows Server 2012 R2

オペレーティング システム ソフトウェアを Standard Edition サーバーまたは Enterprise Edition フロントエンド サーバーにインストールします。オペレーティング システムを最新の状態、かつ組織の標準に一致した必須の更新レベルにするために、すべての更新プログラムを適用します。動作要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

> [!NOTE]
> Lync Server 2013 を Windows Server 2012 R2 上で実行するには、Windows Server のレジストリ キーの値の変更が必要な場合があります。この変更は、証明書の適切な動作や、存続可能ブランチ アプライアンスでのクライアントの登録に必要な場合があります。詳細については、<a href="http://support.microsoft.com/kb/2901554" class="uri">http://support.microsoft.com/kb/2901554</a> を参照してください。


## Lync Server 2013 用の追加ソフトウェア

Lync Server 2013 では、オペレーティング システムに必要な更新プログラムに加えて、オペレーティング システムの役割、機能、および操作するソフトウェアが必要です。トポロジの公開および Lync Server 2013 のインストールの前にインストールしておく必要がある追加ソフトウェアの詳細については、「計画」のドキュメントの「[Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。

## すべてのサーバーの役割に必要な追加ソフトウェア

すべてのサーバーの役割に、Windows PowerShell コマンドライン インターフェイス 3.0 および Microsoft .NET Framework 4.5 がインストールされていることも確認する必要があります。

また、Windows PowerShell コマンドライン インターフェイス 3.0 および Microsoft .NET Framework 4.5 は、Lync Server 管理ツールを実行するすべてのコンピューターでも必要です。

## Windows PowerShell 3.0

Lync Server 2013 では、Lync Server トポロジに参加する各コンピューターに Windows PowerShell 3.0 をインストールする必要があります。Windows PowerShell 3.0 のインストールの詳細については、「[Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

> [!NOTE]
> Windows Server 2008 R2 SP1 では、Microsoft .NET Framework 4.5 をインストールする前に Windows PowerShell コマンドライン インターフェイス 3.0 をインストールすることはできません。


## Microsoft .NET Framework 4.5

Windows Server 2012 または Windows Server 2012 R2 で Lync Server 2013 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールするときは、追加手順を 1 つ実行する必要があります。.NET Framework 4.5 をインストールした後、サーバー マネージャーを使用して HTTP アクティブ化をインストールします。

**.NET 4.5 HTTP アクティブ化を Windows Server 2012 または Windows Server 2012 R2 にインストールするには**

1.  \[**スタート**\] メニューから、\[**プログラム**\]、\[**管理ツール**\]、\[**サーバー マネージャー**\] の順にクリックします。

2.  サーバー マネージャーで、\[**機能の概要**\] の \[**機能の追加**\] を選択します。

3.  \[**.NET Framework 4.5**\] を展開します。

4.  \[**WCF アクティブ化**\] がまだ選択されていない場合は選択します。次に、\[**HTTP アクティブ化**\] を選択します。

5.  \[**次へ**\] をクリックし、表示される指示に従ってインストールを完了します。

