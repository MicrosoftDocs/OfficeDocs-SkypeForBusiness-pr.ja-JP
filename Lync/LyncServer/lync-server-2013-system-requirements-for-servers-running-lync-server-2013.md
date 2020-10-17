---
title: 'Lync Server 2013: Lync Server 2013 を実行しているサーバーのシステム要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d25be2132fdaba58024ba58081656b830ea9fe4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497334"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Lync Server 2013 を実行しているサーバーのシステム要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-07-24_

<div>


> [!NOTE]
> ハードウェア要件の詳細については、「 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>」を参照してください。



</div>

Standard Edition と Enterprise Edition のサーバーは、同じソフトウェア要件を共有します。

Lync Server 2013 Enterprise Edition を実行しているサーバーは、主要な組織の展開として大規模な組織を対象としています。 Enterprise Edition サーバーは、1 プールにつき、約 80,000 の所属ユーザーまでの拡張性を有するよう、設計されています。 Lync Server 2013 の Standard Edition を実行しているサーバーは、小規模な組織と、メインの組織展開から離れた場所を対象としています。 1組の Standard Edition サーバーは、最大5000ユーザーをサポートできます。 Standard Edition サーバーと Enterprise Edition サーバーの相違点の詳細については、「 [Deployment の概要 (Lync Server 2013](lync-server-2013-deployment-overview.md))」を参照してください。

<div>

## <a name="operating-system-installation"></a>オペレーティング システムのインストール

<div>


> [!IMPORTANT]
> Lync Server 2013 は、64ビット版でのみ使用できます。これには、64ビットハードウェアと、Windows Server オペレーティングシステムの64ビット版が必要です。 このリリースでは、32ビット版の Lync Server 2013 は利用できません。



</div>

Standard Edition および Enterprise Edition サーバーでは、次のいずれかを使用できます。

  - Windows Server 2008 R2 SP1 または最新のサービスパック

  - Windows Server 2012

  - Windows Server 2012 R2

Standard Edition サーバーまたは Enterprise Edition フロントエンドサーバーに、オペレーティングシステムソフトウェアをインストールします。 オペレーティング システムを最新の状態にするため、そして組織の標準に沿うのに必要な更新レベルにするために、すべての変更プログラムを適用します。 操作要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。

> [!NOTE] 
> Lync Server 2013 では、オペレーティングシステムの一括アップグレードはサポートされていません。  別のプールを展開し、ユーザーを別のオペレーティングシステムを使用して新しいプールに移行する必要があります。

<div>


> [!NOTE]
> Windows Server 2012 R2 で Lync Server 2013 を動作させるには、Windows Server でレジストリキーの値を変更する必要がある場合があります。 この変更は、証明書が正常に機能し、クライアントが存続可能 Branch アプライアンスに登録するために必要になることがあります。 詳細については、「」を参照してください <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> 。



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Lync Server 2013 の追加ソフトウェア

オペレーティングシステムに必要な更新プログラムに加えて、Lync Server 2013 では、オペレーティングシステムの役割、機能、およびソフトウェアを運用する必要があります。 トポロジを公開して Lync Server 2013 をインストールする前にインストールする必要がある追加ソフトウェアの詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md) 」を参照してください。

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>すべてのサーバーの役割に必要な追加ソフトウェア

すべてのサーバーの役割についても、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 がインストールされていることを確認する必要があります。

また、Lync Server 管理ツールを実行するコンピューターでは、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 が必要です。

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 では、Lync Server トポロジに参加する各コンピューターに Windows PowerShell 3.0 をインストールする必要があります。 Windows PowerShell 3.0 のインストールの詳細については、「 [Windows powershell 3.0 を Lync Server 2013 にインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

<div>


> [!NOTE]
> Windows Server &nbsp; 2008 &nbsp; R2 SP1 では、Microsoft .net Framework 4.5 をインストールする前に、windows PowerShell コマンドラインインターフェイス3.0 をインストールすることはできません。



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Windows Server 2012 または Windows Server 2012 R2 上で Lync Server 2013 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、1つの追加の手順を実行する必要があります。 .NET Framework 4.5 をインストールした後、サーバーマネージャーを使用して HTTP アクティブ化をインストールします。

**Windows Server 2012 または Windows Server 2012 R2 に .NET 4.5 HTTP ライセンス認証をインストールするには**

1.  [ **スタート** ] メニューの [ **プログラム**] をクリックし、[ **管理ツール**] をクリックして、[ **サーバーマネージャー**] をクリックします。

2.  サーバーマネージャーの [ **機能の概要**] で、[ **機能の追加**] を選択します。

3.  [ **.Net Framework 4.5**] を展開します。

4.  まだ選択されていない場合は、[ **WCF アクティブ化** ] を選択します。 [ **HTTP アクティブ化**] を選択します。

5.  [ **次へ** ] をクリックし、画面の指示に従ってインストールを完了します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

