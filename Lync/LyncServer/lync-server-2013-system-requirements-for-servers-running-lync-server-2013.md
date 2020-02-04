---
title: 'Lync Server 2013: Lync Server 2013 を実行するサーバーのシステム要件'
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
ms.openlocfilehash: c6566202dbbfa112f884ac1bb8380d1d554ba994
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731607"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Lync Server 2013 を実行するサーバーのシステム要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-07-24_

<div>


> [!NOTE]  
> ハードウェア要件の詳細については、「 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 用のサーバーハードウェアプラットフォーム</A>」を参照してください。



</div>

Standard Edition と Enterprise Edition のサーバーは、同じソフトウェア要件を共有します。

Lync Server 2013、Enterprise Edition を実行しているサーバーは、主要な組織の展開として大規模な組織向けに設計されています。 Enterprise Edition server は、1つのプールあたり約8万のホームユーザーに対応するように設計されています。 Lync Server 2013、Standard エディションを実行しているサーバーは、組織の主要な展開によって小規模の組織やリモートの場所を対象としています。 標準エディションのサーバーの1組は、最大5000ユーザーをサポートできます。 Standard Edition server と Enterprise Edition サーバーの違いの詳細については、「 [Lync Server 2013 の展開の概要](lync-server-2013-deployment-overview.md)」を参照してください。

<div>

## <a name="operating-system-installation"></a>オペレーティングシステムのインストール

<div>


> [!IMPORTANT]  
> Lync Server 2013 は、64ビット版でのみ使用できます。これには、64ビットハードウェアと Windows Server オペレーティングシステムの64ビット版が必要です。 このリリースでは、32ビット版の Lync Server 2013 は使用できません。



</div>

Standard Edition server および Enterprise Edition server では、次のいずれかを使用できます。

  - Windows Server 2008 R2 SP1 または最新の service pack

  - Windows Server 2012

  - Windows Server 2012 R2

Standard Edition Server または Enterprise Edition のフロントエンドサーバーに、オペレーティングシステムソフトウェアをインストールします。 すべての更新プログラムを適用して、オペレーティングシステムを最新の更新プログラムおよび必須の更新レベルにして、組織の標準に準拠させます。 操作要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

> [!NOTE] オペレーティングシステムのインプレースアップグレードは、Lync Server 2013 ではサポートされていません。  別のオペレーティングシステムを使用して、別のプールを展開し、ユーザーを新しいプールに移行する必要があります。

<div>


> [!NOTE]  
> Lync Server 2013 を Windows Server 2012 R2 で動作させるには、Windows Server でレジストリキーの値を変更する必要がある場合があります。 この変更は、証明書が正しく動作するために必要な場合があり、クライアントが Survivable Branch アプライアンスに登録します。 詳細については<A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>、を参照してください。



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Lync Server 2013 のその他のソフトウェア

Lync Server 2013 では、オペレーティングシステムに必要な更新に加えて、オペレーティングシステムの役割、機能、およびソフトウェアの操作が必要になります。 トポロジを公開して Lync Server 2013 をインストールする前にインストールする必要があるその他のソフトウェアの詳細については、計画ドキュメントの「 [Lync server 2013 のその他のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>すべてのサーバーの役割に必要なその他のソフトウェア

すべてのサーバーの役割では、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 がインストールされていることも確認する必要があります。

さらに、Lync Server 管理ツールを実行するコンピューターでは、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 が必要です。

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 では、Lync Server のトポロジに参加する各コンピューターに Windows PowerShell 3.0 をインストールする必要があります。 Windows PowerShell 3.0 のインストールの詳細については、「 [Lync Server 2013 用に Windows powershell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

<div>


> [!NOTE]  
> Windows Server&nbsp;2008&nbsp;R2 SP1 では、Microsoft .net Framework 4.5 をインストールする前に windows PowerShell コマンドラインインターフェイス3.0 をインストールすることはできません。



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Windows Server 2012 または Windows Server 2012 R2 で Lync Server 2013 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、追加の手順を1つ実行する必要があります。 .NET Framework 4.5 がインストールされたら、サーバーマネージャーを使用して、HTTP アクティブ化をインストールします。

**Windows Server 2012 または Windows Server 2012 R2 で .NET 4.5 HTTP ライセンス認証をインストールするには**

1.  [**スタート**] メニューで、[**プログラム**]、[**管理ツール**]、[**サーバーマネージャー**] の順にクリックします。

2.  サーバーマネージャーの [**機能の概要**] で、[**機能の追加**] を選択します。

3.  **.Net Framework 4.5**を展開します。

4.  まだ選択されていない場合は、[ **WCF ライセンス認証**] を選択します。 次に、[ **HTTP ライセンス認証**] を選択します。

5.  [**次へ**] をクリックし、画面の指示に従ってインストールを完了します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

