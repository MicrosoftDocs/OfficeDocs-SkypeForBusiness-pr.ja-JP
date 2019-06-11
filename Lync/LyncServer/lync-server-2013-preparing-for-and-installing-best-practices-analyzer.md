---
title: 'Lync Server 2013: ベストプラクティスアナライザーの準備とインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d1d2f86b579bfb0259c8ad3e4b26b051b47a8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 でのベストプラクティスアナライザーの準備とインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

このトピックで説明されているタスクを実行するには、管理者グループのメンバーとしてログオンしている必要があります。

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>ベストプラクティスアナライザーをインストールするためのシステム要件

Lync Server 2013 のベストプラクティスアナライザーを実行して環境をスキャンするには、コンピューターで次のいずれかのオペレーティングシステムの64ビット版が実行されている必要があります。

  - Windows Server 2008 R2 Service Pack 1 (SP1) 標準オペレーティングシステム

  - Windows Server 2008 R2 SP1 Enterprise オペレーティングシステム

  - Windows Server 2008 R2 SP1 Datacenter オペレーティングシステム

  - Windows Server 2012 Datacenter オペレーティングシステム

  - Windows Server 2012 標準オペレーティングシステム

  - Windows Server 2012 エンタープライズオペレーティングシステム

  - Windows Server 2012 R2 Datacenter オペレーティングシステム

  - Windows Server 2012 R2 Standard オペレーティングシステム

  - Windows Server 2012 R2 Enterprise オペレーティングシステム

  - Windows 8 オペレーティングシステム

  - Windows 7 オペレーティング システム

コンピューターでは、次の操作も実行する必要があります。

  - Microsoft .NET Framework 4.5 Lync Server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。

  - Lync Server 2013、コアコンポーネント。

  - WMI の下位互換性パッケージ。 詳細については、「移行ドキュメントで[WMI 下位互換性パッケージをインストール](install-wmi-backward-compatibility-package.md)する」を参照してください。

  - Windows PowerShell 3.0 詳細については、「展開ドキュメントで[Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

ベストプラクティスアナライザーは、Lync Server 2013、コアコンポーネント、または WMI 下位互換性パッケージを実行していないオペレーティングシステムがサポートされているコンピューターにインストールできますが、これらのコンピューターではベストプラクティスアナライザーを使ってレポートを表示することはできません。スキャンを実行します。

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>インストールするコンピューターを選ぶ

Lync server 2013 のベストプラクティスアナライザーを Lync Server 2013 管理専用のコンピューターにインストールすることをお勧めします。 Lync Server 2013 を実行しているサーバー、または Lync Server 2013 管理ツールを実行している管理コンピューターにツールをインストールすることができます。 Lync Server を実行しているサーバーにツールをインストールする場合は、このツールを使用してそのサーバーのみをスキャンすることをお勧めします。

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>ベストプラクティスアナライザーをインストールする

Lync Server 2013 のベストプラクティスアナライザーをダウンロードでき[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)ます。

ベストプラクティスアナライザーをインストールするには、ツールをインストールするコンピューターで Microsoft インストーラーファイル RtcBPA .msi を起動し、画面の指示に従います。 プログラムファイルをインストールするための既定の\<場所は\>\\、システム\\ドライブのプログラム\\ファイル Lync Server 2013 BPA です。

</div>

</div>

<span> </span>

</div>

</div>

</div>

