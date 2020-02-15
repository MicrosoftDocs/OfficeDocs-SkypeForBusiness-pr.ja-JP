---
title: 'Lync Server 2013: ベストプラクティスアナライザーの準備とインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c97657b42ec4ea26f5300b1d28215d0360b63cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 でのベストプラクティスアナライザーの準備とインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

このトピックで説明するタスクを実行するには、Administrators グループのメンバーとしてログオンする必要があります。

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>ベスト プラクティス アナライザーをインストールするためのシステム要件

Lync Server 2013 を実行するには、ベストプラクティスアナライザーを使用して環境をスキャンするには、次のいずれかのオペレーティングシステムの64ビット版がコンピューターで実行されている必要があります。

  - Windows Server 2008 R2 Service Pack 1 (SP1) Standard オペレーティングシステム

  - Windows Server 2008 R2 SP1 エンタープライズオペレーティングシステム

  - Windows Server 2008 R2 SP1 Datacenter オペレーティングシステム

  - Windows Server 2012 Datacenter オペレーティングシステム

  - Windows Server 2012 Standard オペレーティングシステム

  - Windows Server 2012 エンタープライズオペレーティングシステム

  - Windows Server 2012 R2 Datacenter オペレーティングシステム

  - Windows Server 2012 R2 Standard オペレーティングシステム

  - Windows Server 2012 R2 Enterprise オペレーティングシステム

  - Windows 8 オペレーティングシステム

  - Windows 7 オペレーティング システム

また、以下も実行している必要があります。

  - Microsoft .NET Framework 4.5。 Lync server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。

  - Lync Server 2013、コアコンポーネント。

  - WMI 下位互換パッケージ。 詳細については、「移行」のドキュメントの「 [INSTALL WMI 下位互換パッケージをインストール](install-wmi-backward-compatibility-package.md)する」を参照してください。

  - Windows PowerShell 3.0。 詳細については、「展開」のドキュメントの「 [Windows PowerShell 3.0 For Lync Server 2013 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

ベストプラクティスアナライザーは、Lync Server 2013、コアコンポーネント、または WMI 下位互換パッケージを実行していない、サポートされているオペレーティングシステムを搭載したコンピューターにインストールできますが、これらのコンピューターでベストプラクティスアナライザーを使用しても、レポートを表示することはできません。スキャンを実行する。

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>インストール対象のコンピューターの選択

Lync server 2013 管理専用のコンピューターに Lync Server 2013、ベストプラクティスアナライザーをインストールすることをお勧めします。 Lync Server 2013 を実行しているサーバー、または Lync Server 2013 管理ツールを実行している管理コンピューターに、ツールをインストールすることができます。 Lync Server を実行しているサーバーにツールをインストールする場合は、ツールを使用してそのサーバーのみをスキャンすることをお勧めします。

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>ベスト プラクティス アナライザーのインストール

Lync Server 2013 のベストプラクティスアナライザーをダウンロードすることが[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)できます。

ベスト プラクティス アナライザーをインストールするには、ツールをインストールするコンピューターで Microsoft インストーラー ファイル (RtcBPA.msi) を起動し、画面の指示に従います。 プログラムファイルをインストールする既定の場所は\<、システム\>\\ドライブの\\プログラムファイル Lync\\Server 2013 BPA です。

</div>

</div>

<span> </span>

</div>

</div>

</div>

